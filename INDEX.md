# 📱 Expense Tracker - Complete Android Application

> **A modern, offline-first expense tracking app with automatic SMS parsing, smart limits, and beautiful Material Design UI**

---

## 🎯 What Is This?

This is a **complete, production-ready Android application** that automatically tracks your expenses by reading bank transaction SMS messages. It features:

- ✅ **Automatic SMS parsing** from 14+ Indian banks
- ✅ **Offline-first** with local SQLite storage
- ✅ **Financial year tracking** (April - March)
- ✅ **Smart spending limits** with notifications
- ✅ **Custom reminders** at expense thresholds
- ✅ **Modern Material Design UI**
- ✅ **Privacy-focused** (all data stays local)

---

## 📚 Documentation

### 🚀 Getting Started
- **[Quick Start Guide](QUICKSTART.md)** - Get up and running in 5 minutes ⚡
- **[Installation Guide](INSTALLATION.md)** - Complete setup instructions 🔧
- **[Build Instructions](BUILD.md)** - How to build and deploy 🏗️

### 📖 Learn More
- **[README](README.md)** - Full documentation and user guide 📘
- **[Features](FEATURES.md)** - Detailed feature documentation 🎨
- **[Project Summary](PROJECT_SUMMARY.md)** - What's included and why ✨

---

## ⚡ Quick Start

### Option 1: 5-Minute Setup (Recommended)
```
1. Open Android Studio
2. Open this folder (C:\Users\Dev-Raj\Downloads\App)
3. Wait for Gradle sync
4. Click Run ▶️
5. Grant permissions
```
👉 **[Full Quick Start Guide](QUICKSTART.md)**

### Option 2: Build from Command Line
```powershell
cd "C:\Users\Dev-Raj\Downloads\App"
gradlew assembleDebug
adb install app\build\outputs\apk\debug\app-debug.apk
```
👉 **[Full Build Guide](BUILD.md)**

---

## 📦 What's Included

### Complete Source Code
```
✅ 50+ Kotlin source files
✅ 3,000+ lines of code
✅ MVVM architecture
✅ Room database
✅ Material Design UI
✅ Complete documentation
```

### Key Components
- **SMS Parser** - Intelligent transaction detection
- **Database Layer** - SQLite with Room
- **UI Layer** - Material Design Fragments
- **Notification System** - Smart alerts
- **Background Tasks** - Efficient processing

### Documentation Files
1. **INDEX.md** ← You are here!
2. **[QUICKSTART.md](QUICKSTART.md)** - 5-minute setup
3. **[README.md](README.md)** - Complete user guide
4. **[FEATURES.md](FEATURES.md)** - Feature documentation
5. **[INSTALLATION.md](INSTALLATION.md)** - Full setup guide
6. **[BUILD.md](BUILD.md)** - Build instructions
7. **[PROJECT_SUMMARY.md](PROJECT_SUMMARY.md)** - Project overview

---

## 🎨 Screenshots Preview

### Dashboard
```
┌─────────────────────────────────┐
│  Financial Year (Apr-Mar)       │
│  Total: ₹1,50,000               │
│  Credit: ₹2,00,000 | Debit: ₹50K│
└─────────────────────────────────┘

Today        This Week
₹5,000       ₹25,000
₹2,000       ₹15,000

Recent Transactions
• ₹500 - Amazon - Today
• ₹1,200 - Grocery - Yesterday
```

### Features at a Glance
- 🏦 **14+ Banks Supported** - SBI, HDFC, ICICI, Axis, and more
- 📊 **Smart Analytics** - Daily, weekly, monthly summaries
- 🔔 **Intelligent Alerts** - Limit notifications and reminders
- 🎨 **Beautiful UI** - Material Design 3
- 🔒 **Privacy First** - No internet, all local

---

## 🛠️ Technology Stack

```
Language:        Kotlin 100%
Architecture:    MVVM + Repository
Database:        Room (SQLite)
UI:              Material Design Components
Async:           Coroutines + Flow
Navigation:      Navigation Component
Background:      WorkManager
Min SDK:         24 (Android 7.0)
Target SDK:      34 (Android 14)
```

---

## 📋 Prerequisites

### To Build
- Windows 10 or later
- Android Studio Hedgehog or later
- JDK 17
- 8 GB RAM (16 GB recommended)

### To Run
- Android device with Android 7.0+
- SMS capability
- 50 MB storage space

---

## 🚦 Three Ways to Start

### 1️⃣ For Quick Testing (5 min)
**Read**: [QUICKSTART.md](QUICKSTART.md)
```
→ Open in Android Studio
→ Click Run
→ Test on device/emulator
```

### 2️⃣ For Complete Setup (30 min)
**Read**: [INSTALLATION.md](INSTALLATION.md)
```
→ Install Android Studio
→ Configure environment
→ Build and deploy
```

### 3️⃣ For Understanding (1 hour)
**Read**: [README.md](README.md) + [FEATURES.md](FEATURES.md)
```
→ Learn architecture
→ Understand features
→ Customize code
```

---

## 🎯 Use Cases

### For Personal Use
- Track daily expenses automatically
- Set monthly spending limits
- Get notified before exceeding budget
- View financial year summaries

### For Learning
- Study MVVM architecture
- Learn Room database
- Understand SMS parsing
- Practice Material Design

### For Customization
- Add new banks
- Customize UI themes
- Add new features
- Extend functionality

---

## 📊 Project Stats

| Metric | Value |
|--------|-------|
| Total Files | 60+ |
| Source Files | 50+ |
| Lines of Code | 3,000+ |
| Documentation | 6 guides |
| Screens | 3 main + dialogs |
| Database Tables | 4 |
| Supported Banks | 14+ |
| Min Android Version | 7.0 (API 24) |

---

## 🔍 Feature Highlights

### Automatic SMS Parsing
```kotlin
SMS: "Your A/c XX1234 debited by Rs.500 on 31-Dec-25"
     ↓
Parsed Transaction:
- Amount: ₹500
- Type: Debit
- Account: ****1234
- Date: Dec 31, 2025
```

### Smart Limits
```
Set: Daily limit ₹5,000 (Alert at 80%)
Status: Spent ₹4,200 (84%)
Action: Notification sent ✅
```

### Financial Year Tracking
```
FY 2025-26: Apr 2025 - Mar 2026
Credit: ₹5,00,000
Debit: ₹3,50,000
Balance: ₹1,50,000
```

---

## 🗺️ Navigation Guide

### New to Android Development?
```
1. Read QUICKSTART.md
2. Open project in Android Studio
3. Run on emulator
4. Explore the code
5. Read README.md for details
```

### Experienced Developer?
```
1. Skim PROJECT_SUMMARY.md
2. Review architecture in source
3. Build and customize
4. Check FEATURES.md for details
```

### Just Want to Use It?
```
1. Follow QUICKSTART.md
2. Build and install
3. Grant permissions
4. Import SMS
5. Start tracking!
```

---

## 📞 Support & Help

### ⚠️ Installation Issues (Google Play Protect)
If you see **"Blocked by Play Protect"** when installing:
1. This is normal because this is a test app not from the Play Store.
2. Click **"More details"** (the small arrow 🔽).
3. Click **"Install anyway"**.
4. The app will install successfully.

### Documentation
- **Setup Issues**: [INSTALLATION.md](INSTALLATION.md) → Troubleshooting
- **Build Errors**: [BUILD.md](BUILD.md) → Common Issues
- **Feature Questions**: [FEATURES.md](FEATURES.md) → FAQ
- **Usage Help**: [README.md](README.md) → Usage Guide

### Debugging
```powershell
# View logs
adb logcat | Select-String "ExpenseTracker"

# Check device
adb devices

# Reinstall app
adb uninstall com.expensetracker.app
adb install app.apk
```

---

## 🎓 Learning Resources

### Architecture
- `data/model/` - Data classes
- `data/dao/` - Database access
- `data/repository/` - Data layer
- `viewmodel/` - Business logic
- `ui/` - Presentation layer

### Key Files to Study
1. **SmsParser.kt** - SMS parsing logic
2. **ExpenseDatabase.kt** - Database setup
3. **DashboardViewModel.kt** - MVVM example
4. **TransactionRepository.kt** - Repository pattern
5. **MainActivity.kt** - Navigation setup

---

## 🚀 Next Steps

### After Setup
1. ✅ Build and run the app
2. ✅ Import SMS history
3. ✅ Set a spending limit
4. ✅ Create a reminder
5. ✅ Explore all screens

### For Customization
1. 📝 Change colors/theme
2. 🏦 Add more banks
3. 📊 Add charts/graphs
4. 💾 Add export feature
5. ☁️ Add backup (optional)

### For Deployment
1. 🔑 Create signing key
2. 📦 Build release APK
3. 🧪 Test thoroughly
4. 📱 Install on devices
5. 🌟 Share or publish!

---

## ✨ What Makes This Special?

### Complete Solution
✅ All features working  
✅ Production-ready code  
✅ Comprehensive documentation  
✅ No dependencies on external services  

### Best Practices
✅ MVVM architecture  
✅ Clean code principles  
✅ Efficient database design  
✅ Material Design guidelines  

### Privacy Focused
✅ Offline-first  
✅ Local data storage  
✅ No analytics  
✅ No data collection  

### Developer Friendly
✅ Well-documented code  
✅ Clear architecture  
✅ Easy to customize  
✅ Ready to extend  

---

## 📄 License & Credits

This project is for personal use. All rights reserved.

**Created**: December 31, 2025  
**Version**: 1.0.0  
**Developer**: For Dev-Raj

---

## 🎉 Ready to Start?

Choose your path:

### 🚀 Quick Start (5 min)
👉 **[QUICKSTART.md](QUICKSTART.md)**

### 🔧 Full Setup (30 min)
👉 **[INSTALLATION.md](INSTALLATION.md)**

### 📚 Deep Dive (1 hour)
👉 **[README.md](README.md)** + **[FEATURES.md](FEATURES.md)**

---

<div align="center">

### 📱 Expense Tracker

**Modern • Private • Powerful**

*Track expenses automatically with SMS parsing*

**[Get Started →](QUICKSTART.md)**

---

Made with ❤️ using Kotlin and Material Design

</div>
