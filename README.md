# RN THEOplayer Demo Phone

https://github.com/tiamitrai/rntheodemophone/raw/main/demo.mov

A React Native demo app integrating [THEOplayer](https://www.theoplayer.com/) for HLS video playback, built with [`@react-native-community/cli`](https://github.com/react-native-community/cli).

## Stack

- **React Native** 0.87.1
- **react-native-theoplayer** 11.x
- **react-native-dotenv** — injects `.env` variables at build time

## Prerequisites

- Node >= 22.11.0
- [React Native environment setup](https://reactnative.dev/docs/set-up-your-environment) completed
- For iOS: CocoaPods installed

## Environment Setup

Create a `.env` file in the project root:

```sh
LICENSE="your-theoplayer-license-key"
```

> The `LICENSE` value is your THEOplayer React Native license. It is injected at build time via `react-native-dotenv` — never commit `.env` to version control.

## Getting Started

### 1. Install dependencies

```sh
npm install
```

### 2. iOS — install CocoaPods

First time setup:

```sh
bundle install
bundle exec pod install
```

After any native dependency update:

```sh
bundle exec pod install
```

### 3. Start Metro

```sh
npm start

# Reset cache if you changed babel.config.js or .env
npm start -- --reset-cache
```

### 4. Run the app

**Android:**

```sh
npm run android
```

**iOS:**

```sh
npm run ios
```

## Project Structure

```
rntheodemophone/
├── App.tsx          # Entry point — THEOplayer setup and source config
├── babel.config.js  # Babel config with react-native-dotenv plugin
├── env.d.ts         # TypeScript types for @env module
├── .env             # THEOplayer license (not committed)
└── ios/             # iOS native project
```

## Troubleshooting

**Version mismatch errors** — ensure all `@react-native/*` packages are on the same version as `react-native`:

```sh
npm install react-native@0.87.1 @react-native/metro-config@0.87.1 @react-native/new-app-screen@0.87.1 --legacy-peer-deps
```

**Metro cache issues** — reset cache after changing Babel config or `.env`:

```sh
npm start -- --reset-cache
```

**iOS build failures** — re-run pod install:

```sh
bundle exec pod install
```

For more, see the [React Native Troubleshooting](https://reactnative.dev/docs/troubleshooting) page.
