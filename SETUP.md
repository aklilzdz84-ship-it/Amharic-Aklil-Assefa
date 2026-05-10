# Complete Installation Guide - Step by Step

## Prerequisites

### Install Required Tools

#### 1. Install Flutter
```bash
# macOS
brew install flutter

# Windows
# Download from: https://flutter.dev/docs/get-started/install/windows
# Then add Flutter to PATH

# Linux
sudo apt-get install flutter
```

#### 2. Install Android SDK
```bash
# Install Android Studio (includes SDK)
# macOS: brew install --cask android-studio
# Or download: https://developer.android.com/studio

# Or install command-line tools only
```

#### 3. Install ADB (Android Debug Bridge)
```bash
# macOS
brew install android-platform-tools

# Windows (via Chocolatey)
choco install adb

# Linux
sudo apt-get install android-tools-adb
```

## Step 1: Prepare Your Android Device

1. **Enable Developer Mode:**
   - Open Settings → About Phone
   - Tap "Build Number" 7 times
   - Go back to Settings → Developer Options
   - Enable "USB Debugging"
   - Enable "Install via USB"

2. **Connect via USB:**
   - Connect your phone to your computer with a USB cable
   - Select "Transfer files" or "File Transfer" mode when prompted
   - Tap "Allow" on your phone to grant USB debugging access

## Step 2: Verify Connection

```bash
adb devices

# You should see:
# List of attached devices
# emulator-5554          device
# (or your device ID)
```

## Step 3: Clone the Repository

```bash
git clone https://github.com/aklilzdz84-ship-it/Amharic-Aklil-Assefa.git
cd Amharic-Aklil-Assefa
```

## Step 4: Install Flutter Dependencies

```bash
flutter pub get
```

## Step 5: Build the APK

### Option A: Debug APK (Faster, for testing)
```bash
flutter build apk

# APK location: build/app/outputs/flutter-apk/app-debug.apk
```

### Option B: Release APK (Recommended for distribution)
```bash
flutter build apk --release

# APK location: build/app/outputs/flutter-apk/app-release.apk
```

## Step 6: Install on Your Device

### Quick Installation (Recommended)
```bash
# Install directly from Flutter
flutter install

# Or manually:
adb install -r build/app/outputs/flutter-apk/app-debug.apk

# For release APK:
adb install -r build/app/outputs/flutter-apk/app-release.apk
```

## Step 7: Run the App

### From Flutter CLI
```bash
flutter run

# Or on specific device:
flutter run -d <device-id>
```

### From Your Phone
- Look for "Amharic Aklil Assefa" in your app drawer
- Tap to open the app
- Enter Amharic text and tap "Speak"

## Troubleshooting

### Device not recognized
```bash
# Restart ADB server
adb kill-server
adb start-server

# Check again
adb devices
```

### Installation fails with "INSTALL_FAILED_INVALID_APK"
```bash
# Uninstall previous version
adb uninstall com.aklilzdz84.amharic_aklil_assefa

# Rebuild and install
flutter build apk --release
adb install build/app/outputs/flutter-apk/app-release.apk
```

### APK won't open
1. Go to Settings → Apps → Amharic Aklil Assefa
2. Clear Cache and Data
3. Try opening again
4. Grant permissions if prompted

### USB connection issues
- Try a different USB cable
- Disable USB Debugging and re-enable it
- Restart your phone
- Update Android drivers (Windows)

## Verify Installation

```bash
# Check if app is installed
adb shell pm list packages | grep aklil

# Launch app manually
adb shell am start -n com.aklilzdz84.amharic_aklil_assefa/.MainActivity

# View app logs
adb logcat | grep amharic_aklil_assefa
```

## Share the APK

Once built, you can share the APK file:
- **Debug APK:** `build/app/outputs/flutter-apk/app-debug.apk` (for testing)
- **Release APK:** `build/app/outputs/flutter-apk/app-release.apk` (for distribution)

## Next Steps

1. ✅ Build APK
2. ✅ Install on device
3. ✅ Test the app
4. ✅ Share with others or upload to Play Store

## Need Help?

- Flutter Docs: https://flutter.dev/docs
- Android Debug Bridge: https://developer.android.com/studio/command-line/adb
- GitHub Issues: https://github.com/aklilzdz84-ship-it/Amharic-Aklil-Assefa/issues
