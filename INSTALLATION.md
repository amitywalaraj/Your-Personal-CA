# 🔧 Complete Setup & Installation Guide

## Table of Contents
1. [System Requirements](#system-requirements)
2. [Installing Android Studio](#installing-android-studio)
3. [Setting Up the Project](#setting-up-the-project)
4. [Building the App](#building-the-app)
5. [Running on Device](#running-on-device)
6. [Troubleshooting](#troubleshooting)

---

## System Requirements

### Minimum Requirements
- **OS**: Windows 10 or later
- **RAM**: 8 GB (16 GB recommended)
- **Storage**: 10 GB free space
- **Processor**: Intel Core i5 or equivalent
- **Java**: JDK 17 (bundled with Android Studio)

### Android Device Requirements
- **Android Version**: 7.0 (Nougat) or higher
- **Storage**: 50 MB free space
- **SMS**: Active SMS capability
- **Permissions**: SMS, Notifications

---

## Installing Android Studio

### Step 1: Download Android Studio
1. Visit: https://developer.android.com/studio
2. Click "Download Android Studio"
3. Accept terms and download

### Step 2: Install Android Studio
1. Run the downloaded installer
2. Follow installation wizard
3. Choose "Standard" installation
4. Wait for SDK components to download
5. Click "Finish"

### Step 3: Configure Android Studio
```
1. Launch Android Studio
2. Do not open any project yet
3. Click "More Actions" > "SDK Manager"
4. Check these are installed:
   - Android SDK Build-Tools 34
   - Android SDK Platform 34
   - Android SDK Platform-Tools
   - Android SDK Tools
5. Click "Apply" if anything is missing
```

### Step 4: Verify Installation
```powershell
# Open terminal and verify
adb version
# Should show: Android Debug Bridge version X.X.X
```

---

## Setting Up the Project

### Option A: Direct from Folder (Recommended)

1. **Open Android Studio**
   ```
   Launch Android Studio
   Click "Open" (not "New Project")
   ```

2. **Navigate to Project**
   ```
   Browse to: C:\Users\Dev-Raj\Downloads\App
   Click "OK"
   ```

3. **Wait for Gradle Sync**
   ```
   Bottom right corner shows progress
   "Gradle sync completed successfully" appears
   This may take 5-10 minutes first time
   ```

4. **Install Dependencies**
   ```
   Android Studio will automatically download:
   - Kotlin plugin
   - Required libraries
   - Build tools
   ```

### Option B: From ZIP file

1. **Extract ZIP**
   ```
   Right-click downloaded ZIP
   Extract All > Choose location
   ```

2. **Follow Option A steps**

---

## Building the App

### Method 1: Using Android Studio GUI

1. **Build Debug Version**
   ```
   Menu: Build > Make Project
   Or press: Ctrl+F9
   Wait for "Build completed successfully"
   ```

2. **Build Release Version**
   ```
   Menu: Build > Generate Signed Bundle / APK
   Choose: APK
   Click: Create new keystore (first time)
   Fill in details and remember password
   Click: Next > Finish
   ```

### Method 2: Using Command Line

```powershell
# Navigate to project
cd "C:\Users\Dev-Raj\Downloads\App"

# Build debug APK
gradlew assembleDebug

# Build release APK
gradlew assembleRelease

# Clean build
gradlew clean build
```

### APK Locations
```
Debug APK:
app\build\outputs\apk\debug\app-debug.apk

Release APK:
app\build\outputs\apk\release\app-release.apk
```

---

## Running on Device

### Option 1: Physical Android Device

#### Step 1: Enable Developer Mode
```
On your Android phone:
1. Go to Settings
2. About Phone
3. Tap "Build Number" 7 times
4. "You are now a developer!" appears
```

#### Step 2: Enable USB Debugging
```
1. Settings > System > Developer Options
2. Enable "USB Debugging"
3. Enable "Install via USB"
```

#### Step 3: Connect Device
```
1. Connect phone to PC via USB cable
2. On phone, tap "Allow USB debugging"
3. Check "Always allow from this computer"
4. Tap "OK"
```

#### Step 4: Verify Connection
```powershell
# In terminal
adb devices

# Should show:
List of devices attached
ABC123XYZ    device
```

#### Step 5: Install and Run
```
In Android Studio:
1. Click device dropdown (top toolbar)
2. Select your device name
3. Click green Run button (▶️)
4. Wait for "App installed" message
```

### Option 2: Android Emulator

#### Step 1: Create Virtual Device
```
In Android Studio:
1. Tools > Device Manager
2. Click "Create Device"
3. Choose "Phone" category
4. Select "Pixel 6" (recommended)
5. Click "Next"
```

#### Step 2: Select System Image
```
1. Choose "API Level 33" (Tiramisu)
2. Click "Download" if not installed
3. Wait for download
4. Click "Next"
```

#### Step 3: Configure and Create
```
1. Give it a name (e.g., "Test Phone")
2. Click "Finish"
3. Click "Play" button to start emulator
```

#### Step 4: Run App
```
1. Wait for emulator to fully boot
2. Click Run button in Android Studio
3. App installs and launches automatically
```

### Option 3: Install APK Manually

```powershell
# Build APK first
cd "C:\Users\Dev-Raj\Downloads\App"
gradlew assembleDebug

# Install to device
adb install app\build\outputs\apk\debug\app-debug.apk

# Launch app
adb shell am start -n com.expensetracker.app/.ui.MainActivity
```

---

## First Time Setup

### On App Launch

1. **Permission Dialog Appears**
   ```
   Title: "Permission Required"
   Message: "This app needs SMS permission..."
   Click: "Grant Permission"
   ```

2. **System Permission Dialog**
   ```
   "Allow Expense Tracker to access SMS?"
   Select: "Allow"
   ```

3. **Notification Permission (Android 13+)**
   ```
   "Allow notifications?"
   Select: "Allow"
   ```

4. **Initial Setup**
   ```
   1. App opens to Dashboard (initially empty)
   2. Navigate to Settings (bottom navigation)
   3. Click "Import SMS History"
   4. Wait for import to complete
   5. Return to Dashboard to see data
   ```

---

## Troubleshooting

### Problem: Gradle Sync Failed

**Solution 1: Update Gradle Wrapper**
```powershell
cd "C:\Users\Dev-Raj\Downloads\App"
gradlew wrapper --gradle-version 8.1
```

**Solution 2: Invalidate Caches**
```
In Android Studio:
File > Invalidate Caches > Invalidate and Restart
```

**Solution 3: Check Internet**
```
Gradle needs internet for first-time setup
Check firewall/proxy settings
```

### Problem: Build Failed - SDK Not Found

**Solution:**
```
1. Tools > SDK Manager
2. Check "Android SDK Location" is set
3. Install missing SDK components
4. Click "Apply"
5. Rebuild project
```

### Problem: Device Not Detected

**Solution 1: Driver Issues (Windows)**
```
1. Device Manager > Android Device
2. Right-click > Update Driver
3. Browse > Let me pick > Show All Devices
4. Select "Android ADB Interface"
```

**Solution 2: Reset ADB**
```powershell
adb kill-server
adb start-server
adb devices
```

**Solution 3: Change USB Mode**
```
On phone:
1. Notification shade
2. USB options
3. Select "File Transfer" or "PTP"
```

### Problem: App Crashes on Launch

**Solution 1: Check Android Version**
```
App requires Android 7.0+
Check: Settings > About Phone > Android Version
```

**Solution 2: Clear App Data**
```
Settings > Apps > Expense Tracker
Storage > Clear Data
Relaunch app
```

**Solution 3: Check Logcat**
```powershell
adb logcat | Select-String "AndroidRuntime"
# Look for error messages
```

### Problem: Permissions Not Working

**Solution:**
```
1. Uninstall app from device
2. Reinstall from Android Studio
3. Grant all permissions when prompted
4. Or manually:
   Settings > Apps > Expense Tracker > Permissions
   Enable all required permissions
```

### Problem: No SMS Being Detected

**Solution 1: Check Permissions**
```
Phone Settings > Apps > Expense Tracker > Permissions
Enable both:
- SMS (Read)
- SMS (Receive)
```

**Solution 2: Test SMS Format**
```
Send this test SMS:
"Your A/c XX1234 debited by Rs.500.00 on 31-Dec-25"
```

**Solution 3: Enable in Settings**
```
In app:
Settings > Enable SMS Reading (toggle ON)
```

### Problem: Build Takes Too Long

**Solution: Optimize Gradle**
```
Edit: gradle.properties
Add these lines:
org.gradle.daemon=true
org.gradle.parallel=true
org.gradle.configureondemand=true
org.gradle.jvmargs=-Xmx4096m
```

### Problem: Out of Memory

**Solution:**
```
Increase heap size in gradle.properties:
org.gradle.jvmargs=-Xmx4096m -XX:MaxMetaspaceSize=512m
```

---

## Advanced Configuration

### Creating Release APK with Signing

1. **Generate Keystore**
```powershell
keytool -genkey -v -keystore expense-tracker.keystore -alias expense-tracker -keyalg RSA -keysize 2048 -validity 10000
```

2. **Configure build.gradle**
```gradle
android {
    signingConfigs {
        release {
            storeFile file('expense-tracker.keystore')
            storePassword 'YourPassword'
            keyAlias 'expense-tracker'
            keyPassword 'YourPassword'
        }
    }
    buildTypes {
        release {
            signingConfig signingConfigs.release
            minifyEnabled true
            shrinkResources true
        }
    }
}
```

3. **Build Signed APK**
```powershell
gradlew assembleRelease
```

### Enable ProGuard/R8 Optimization

Edit `app/build.gradle`:
```gradle
buildTypes {
    release {
        minifyEnabled true
        shrinkResources true
        proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
    }
}
```

---

## Verification Checklist

After setup, verify:

- [ ] Android Studio opens without errors
- [ ] Project syncs successfully
- [ ] Build completes without errors
- [ ] Device/emulator detected by ADB
- [ ] App installs on device
- [ ] App launches without crashes
- [ ] Permissions can be granted
- [ ] SMS import works
- [ ] Dashboard shows data
- [ ] Navigation works between screens
- [ ] Notifications appear when triggered

---

## Getting Help

### Resources
- **Official Docs**: [README.md](README.md)
- **Quick Start**: [QUICKSTART.md](QUICKSTART.md)
- **Features**: [FEATURES.md](FEATURES.md)
- **Build Info**: [BUILD.md](BUILD.md)

### Logs and Debugging
```powershell
# View all logs
adb logcat

# Filter by app
adb logcat | Select-String "ExpenseTracker"

# Save to file
adb logcat > logs.txt
```

### Common Commands
```powershell
# Check device
adb devices

# Install APK
adb install -r app.apk

# Uninstall app
adb uninstall com.expensetracker.app

# Clear app data
adb shell pm clear com.expensetracker.app

# Launch app
adb shell am start -n com.expensetracker.app/.ui.MainActivity

# View database
adb shell "run-as com.expensetracker.app sqlite3 databases/expense_tracker_database"
```

---

## Success!

If you've completed all steps:
- ✅ Android Studio installed and configured
- ✅ Project opened and synced
- ✅ App built successfully
- ✅ App running on device/emulator
- ✅ All features working

**🎉 You're ready to use and customize the Expense Tracker app!**

---

**Setup Time**: 30-60 minutes (first time)  
**Difficulty**: Intermediate  
**Last Updated**: December 31, 2025
