# Expense Tracker - Build Instructions

## Prerequisites
- Android Studio Hedgehog (2023.1.1) or later
- JDK 17
- Android SDK 34
- Gradle 8.1+

## Building the Application

### Option 1: Using Android Studio
1. Open Android Studio
2. Select "Open Project"
3. Navigate to this directory
4. Wait for Gradle sync
5. Click "Build > Make Project"
6. Click "Run" to install on device/emulator

### Option 2: Using Command Line

#### Debug Build
```bash
# Windows
gradlew assembleDebug

# The APK will be at: app\build\outputs\apk\debug\app-debug.apk
```

#### Release Build
```bash
# Windows
gradlew assembleRelease

# The APK will be at: app\build\outputs\apk\release\app-release.apk
```

#### Clean Build
```bash
gradlew clean build
```

#### Install to Device
```bash
# Install debug build
gradlew installDebug

# Install release build
gradlew installRelease
```

## Running the Application

### From Android Studio
1. Connect Android device or start emulator
2. Select device from dropdown
3. Click Run (▶️) button

### From Command Line
```bash
# Ensure device is connected
adb devices

# Install and run
gradlew installDebug
adb shell am start -n com.expensetracker.app/.ui.MainActivity
```

## Testing

### Unit Tests
```bash
gradlew test
```

### Instrumented Tests
```bash
gradlew connectedAndroidTest
```

## Common Issues

### Gradle Sync Failed
- Check internet connection
- Update Gradle wrapper: `gradlew wrapper --gradle-version 8.1`
- Invalidate caches: File > Invalidate Caches > Invalidate and Restart

### Build Failed
- Clean project: `gradlew clean`
- Check JDK version: `java -version` (should be 17)
- Update Android SDK tools

### App Crashes on Launch
- Check permissions in AndroidManifest.xml
- Verify minimum SDK version matches device
- Check logcat for errors: `adb logcat`

## Configuration

### Signing (for Release)
1. Create keystore:
```bash
keytool -genkey -v -keystore expense-tracker.keystore -alias expense-tracker -keyalg RSA -keysize 2048 -validity 10000
```

2. Add to `app/build.gradle`:
```gradle
android {
    signingConfigs {
        release {
            storeFile file('expense-tracker.keystore')
            storePassword 'your_password'
            keyAlias 'expense-tracker'
            keyPassword 'your_password'
        }
    }
    buildTypes {
        release {
            signingConfig signingConfigs.release
        }
    }
}
```

## Performance Optimization

### Enable R8 (Release builds)
Already configured in `app/build.gradle`:
```gradle
buildTypes {
    release {
        minifyEnabled false  // Set to true for optimization
        shrinkResources false  // Set to true to remove unused resources
        proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
    }
}
```

## Build Variants

- **debug**: For development and testing
- **release**: For production distribution

Switch variants in Android Studio:
Build > Select Build Variant > Choose debug/release
