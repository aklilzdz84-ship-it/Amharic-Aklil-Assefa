# Detailed Installation Guide - Amharic Aklil Assefa

## Prerequisites

Before installing the APK, ensure you have:

1. **Android Device** with Android 5.0 (API Level 21) or higher
2. **USB Cable** to connect your device
3. **ADB (Android Debug Bridge)** installed on your computer
4. **Developer Mode** enabled on your Android device

## Step 1: Enable Developer Mode on Android Device

1. Open **Settings**
2. Scroll down to **About Phone**
3. Find **Build Number** and tap it 7 times
4. You should see "You are now a developer"
5. Go back to **Settings** > **Developer Options**
6. Enable **USB Debugging**

## Step 2: Install ADB

### Windows
- Download Android Studio or Android SDK Tools
- Or install via Chocolatey: `choco install adb`

### macOS
- Install via Homebrew: `brew install android-platform-tools`

### Linux
- Install via apt: `sudo apt-get install android-tools-adb`

## Step 3: Connect Your Device

```bash
# Connect your phone via USB cable

# Verify connection
adb devices

# You should see output like:
# List of attached devices
# emulator-5554          device
# or your device ID
```

## Step 4: Install the APK

```bash
# Navigate to the APK directory
cd build/app/outputs/flutter-apk/

# Install the APK
adb install app-release.apk

# Success message:
# Success
```

## Step 5: Launch the App

1. Disconnect USB cable
2. Find "Amharic Aklil Assefa" app on your phone
3. Tap to open

## Troubleshooting

### Device not recognized by ADB

```bash
# Restart ADB server
adb kill-server
adb start-server

# Try again
adb devices
```

### Installation fails with "INSTALL_FAILED_INVALID_APK"

- Delete old APK: `adb uninstall com.example.amharic_aklil_assefa`
- Rebuild APK: `flutter build apk --release`
- Try installing again

### APK won't open after installation

- Go to Settings > Apps > Amharic Aklil Assefa
- Clear cache and data
- Reopen app

## Building from Source

If you need to rebuild the APK:

```bash
# Get dependencies
flutter pub get

# Build APK
flutter build apk --release

# APK location: build/app/outputs/flutter-apk/app-release.apk
```

## Support

For issues or questions, please visit:
https://github.com/aklilzdz84-ship-it/Amharic-Aklil-Assefa/issues
