# BaseProjTsExpoEas - Expo + TypeScript + EAS Base Project

A ready-to-use base project template for React Native development with TypeScript and Expo Application Services (EAS) builds.

## Project Features

- ✅ **React Native** with TypeScript
- ✅ **Expo** (v54.0.33)
- ✅ **EAS Build** configured for internal testing and production deployment
- ✅ **Babel** with module-resolver for clean imports (`@/` aliases)
- ✅ **Ready-to-build** - Just `npm install` and go

## Initial Setup

### 1. Install Expo CLI (if not already installed)

```bash
npm install -g expo-cli
```

### 2. Authenticate with Expo

```bash
eas login
```

Create an Expo account or log in with your existing account.

### 3. Update app.json with Your Expo Username

Edit `app.json` and replace `YOUR_EXPO_USERNAME` with your actual Expo account username:

```json
{
  "expo": {
    "owner": "your-expo-username",
    ...
  }
}
```

### 4. Install Dependencies

```bash
npm install --legacy-peer-deps
```

### 5. Start Development

```bash
npm start
```

## Using as a Project Template

### Copy and Rename

1. Copy this entire directory to a new location
2. Rename the folder to your new project name

### Quick Setup in New Project

1. Open the new project directory
2. Update `app.json`:
   - Change `"name"` to your project name
   - Change `"slug"` to a URL-safe version of your project name
   - Keep or update `"owner"` with your Expo username

3. Run:

   ```bash
   npm install --legacy-peer-deps
   ```

4. Start development:
   ```bash
   npm start
   ```

## Available Scripts

```bash
# Development
npm start          # Start Expo dev server
npm run android    # Run on Android
npm run ios        # Run on iOS
npm run web        # Run on Web

# EAS Builds
npm run build                          # Full build (all platforms)
npm run build:android                  # Android build
npm run build:ios                      # iOS build
npm run build:android:preview          # Android preview build
npm run build:ios:preview              # iOS preview build
npm run build:android:production       # Android production build
npm run build:ios:production           # iOS production build
```

## EAS Build Profiles

### Development

- For development client builds
- Quick iteration and testing
- Distributes internally

### Preview

- For QA and stakeholder testing
- Fully functional production build
- Distributes internally (via EAS)

### Production

- For app store submission
- Optimized production build
- Distribution to App Store / Google Play

## Project Structure

```
BaseProjTsExpoEas/
├── App.tsx              # Main app component
├── index.ts             # App entry point
├── app.json             # Expo configuration
├── eas.json             # EAS build configuration
├── babel.config.js      # Babel configuration
├── tsconfig.json        # TypeScript configuration
├── package.json         # Dependencies and scripts
├── assets/              # Icons, splash screens, images
└── README.md            # This file
```

## Module Aliases

Use `@/` prefix for clean imports from the project root:

```typescript
// Instead of:
import MyComponent from "../../../components/MyComponent";

// Use:
import MyComponent from "@/components/MyComponent";
```

## Useful Links

- [Expo Documentation](https://docs.expo.dev/versions/v54.0.0/)
- [EAS Build Documentation](https://docs.expo.dev/build/introduction/)
- [React Native Docs](https://reactnative.dev/)
- [TypeScript Docs](https://www.typescriptlang.org/)

## Troubleshooting

### Issue: `eas login` fails

- Make sure you have an Expo account at https://expo.dev
- Check your internet connection

### Issue: Build fails with credentials error

- Run `eas credentials` to configure credentials for iOS/Android
- Ensure your `app.json` has the correct `owner` field

### Issue: Module not found with `@/` alias

- Verify the path in your import statement matches the actual file location
- Check that `babel.config.js` has the module-resolver plugin configured

## Notes

- This project uses `--legacy-peer-deps` due to dependency compatibility
- Requires Node.js 16+ and npm 7+
- Always run `npm install --legacy-peer-deps` when setting up a new project from this template
