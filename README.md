# EduBus - Expo App 👋

This is an [Expo](https://expo.dev) project created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## CI/CD Setup

This project is configured with EAS (Expo Application Services) for continuous integration and deployment.

### Build Profiles

- **development**: For development builds with development client
- **preview**: For internal testing builds (APK for Android)
- **production**: For production builds

### Workflows

1. **Create Production Builds** (`.eas/workflows/create-production-builds.yml`)
   - Builds production versions for both Android and iOS
   - Trigger manually from Expo Dashboard

2. **Deploy Updates** (`.eas/workflows/deploy-updates.yml`)
   - Deploys updates to existing builds
   - **Tự động trigger khi push code lên branch `main`**
   - Có thể trigger thủ công từ Dashboard

3. **Auto Build on Tag** (`.eas/workflows/auto-build-on-tag.yml`)
   - Tự động build production khi push tag mới (ví dụ: `v1.0.0`)
   - Có thể trigger thủ công từ Dashboard

### How to Use

1. **Manual Build**: Go to Expo Dashboard → Workflows → "Create Production Builds" → Run
2. **Automatic Updates**: Push code lên branch `main` → Tự động deploy updates
3. **Release Build**: Push tag mới (ví dụ: `git tag v1.0.0 && git push origin v1.0.0`) → Tự động build production
4. **Local Development**: Use `npx expo start` for local development

### Cách hoạt động của Auto Update

- Khi bạn push code lên branch `main`, workflow "Deploy Updates" sẽ tự động chạy
- EAS sẽ tạo một update và deploy lên các app đã được build trước đó
- Users sẽ nhận được update mà không cần download app mới từ store

## Get started

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
   npx expo start
   ```

In the output, you'll find options to open the app in a

- [development build](https://docs.expo.dev/develop/development-builds/introduction/)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Expo Go](https://expo.dev/go), a limited sandbox for trying out app development with Expo

You can start developing by editing the files inside the **app** directory. This project uses [file-based routing](https://docs.expo.dev/router/introduction).

## Get a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the **app-example** directory and create a blank **app** directory where you can start developing.

## Learn more

To learn more about developing your project with Expo, look at the following resources:

- [Expo documentation](https://docs.expo.dev/): Learn fundamentals, or go into advanced topics with our [guides](https://docs.expo.dev/guides).
- [Learn Expo tutorial](https://docs.expo.dev/tutorial/introduction/): Follow a step-by-step tutorial where you'll create a project that runs on Android, iOS, and the web.

## Join the community

Join our community of developers creating universal apps.

- [Expo on GitHub](https://github.com/expo/expo): View our open source platform and contribute.
- [Discord community](https://chat.expo.dev): Chat with Expo users and ask questions.
