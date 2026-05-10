# Amharic Aklil Assefa - Text-To-Speech Application

A Flutter-based Text-To-Speech (TTS) application for Amharic language with Android APK support.

## Features

- 🎤 Amharic Text-To-Speech conversion
- 🎯 Simple and intuitive UI
- ⚡ Fast and responsive
- 📱 Android APK distribution

## Quick Start

### Installation via ADB

```bash
# Connect your phone via USB
adb devices  # Should show your phone

# Install APK
adb install build/app/outputs/flutter-apk/app-release.apk
```

### Manual Installation

1. Clone the repository
2. Navigate to project directory
3. Run `flutter pub get`
4. Connect Android device
5. Run `flutter run --release`

## Building APK

```bash
flutter build apk --release
```

The APK will be available at: `build/app/outputs/flutter-apk/app-release.apk`

## Requirements

- Flutter SDK
- Android SDK
- Android device or emulator
- USB cable (for device installation)

## License

MIT License

## Author

aklilzdz84-ship-it
