# Expense Tracker - Android Application

A comprehensive Android expense tracking application with automatic SMS parsing, modern UI, and offline-first architecture.

## 🌟 Features

### Core Functionality
- ✅ **Automatic SMS Parsing**: Reads bank transaction SMS and extracts key details
- ✅ **Offline-First**: All data stored locally using SQLite/Room
- ✅ **Financial Year Tracking**: Track expenses between financial years (April - March)
- ✅ **Transaction Management**: View, filter, and manage all transactions
- ✅ **Dashboard Analytics**: Daily, weekly, monthly, and yearly summaries

### Smart Features
- 🔔 **Transaction Limits**: Set daily, weekly, or monthly spending limits
- ⏰ **Custom Reminders**: Get notified at specific expense thresholds (₹50,000, ₹1,00,000, etc.)
- 📊 **Expense Insights**: Visual representation of spending patterns
- 🔒 **Privacy-First**: All data processed locally on device

### UI/UX
- 🎨 **Modern Material Design**: Clean, minimal interface
- 🌓 **Dark Mode Support**: Automatic theme switching
- ⚡ **Smooth Animations**: Polished transitions and interactions
- 📱 **Responsive Layout**: Optimized for all screen sizes

## 🏗️ Architecture

### Tech Stack
- **Language**: Kotlin
- **Architecture**: MVVM (Model-View-ViewModel)
- **Database**: Room (SQLite)
- **Async**: Coroutines + Flow
- **UI**: Material Design Components, View Binding
- **Navigation**: Navigation Component
- **Background Tasks**: WorkManager

### Project Structure
```
app/
├── data/
│   ├── model/          # Data classes (Transaction, Limit, Reminder)
│   ├── dao/            # Room DAOs
│   ├── database/       # Database setup
│   └── repository/     # Repository pattern
├── ui/
│   ├── adapter/        # RecyclerView adapters
│   └── fragments/      # Dashboard, Transactions, Settings
├── viewmodel/          # ViewModels
├── sms/                # SMS receiver and parser
├── notification/       # Notification system
└── utils/              # Utility classes

```

## 📋 Prerequisites

- Android Studio Arctic Fox or later
- Android SDK 24+ (Android 7.0+)
- Gradle 8.1+
- JDK 17

## 🚀 Setup Instructions

### 1. Clone the Repository
```bash
cd "C:\Users\Dev-Raj\Downloads\App"
```

### 2. Open in Android Studio
1. Open Android Studio
2. Select "Open an Existing Project"
3. Navigate to `C:\Users\Dev-Raj\Downloads\App`
4. Wait for Gradle sync to complete

### 3. Build the Project
```bash
# From project root
gradlew build

# Or from Android Studio
Build > Make Project
```

### 4. Run the Application
1. Connect an Android device or start an emulator
2. Click Run (▶️) in Android Studio
3. Grant required permissions when prompted

## 🔐 Permissions Required

The app requires the following permissions:

- **READ_SMS**: Read existing bank transaction messages
- **RECEIVE_SMS**: Automatically detect new bank transactions
- **POST_NOTIFICATIONS**: Send limit and reminder notifications

## 📱 Usage Guide

### First Launch
1. Grant SMS and notification permissions
2. Import existing SMS history (Settings > Import SMS)
3. Wait for transactions to be parsed and displayed

### Setting Transaction Limits
1. Go to Settings
2. Tap "Add" under Transaction Limits
3. Choose period (Daily/Weekly/Monthly)
4. Set limit amount and threshold percentage
5. Save

### Creating Reminders
1. Go to Settings
2. Tap "Add" under Reminders
3. Set threshold amount (e.g., ₹50,000)
4. Choose notification frequency
5. Save

### Viewing Transactions
1. Dashboard shows summaries for Today, This Week, This Month
2. Transactions tab shows all transactions
3. Tap any transaction for details

## 🎨 UI Components

### Dashboard
- Financial Year summary card
- Period-wise summaries (Today, Week, Month)
- Recent transactions list
- Color-coded credits (green) and debits (red)

### Transactions
- Chronological list of all transactions
- Filter by date, type, or amount
- Swipe actions for quick operations

### Settings
- SMS reading toggle
- Import SMS history
- Transaction limits management
- Reminder configuration
- App preferences

## 🔍 SMS Parsing

The app automatically parses SMS from major Indian banks:

### Supported Banks
- State Bank of India (SBI)
- HDFC Bank
- ICICI Bank
- Axis Bank
- Kotak Mahindra Bank
- Punjab National Bank (PNB)
- Bank of Baroda
- Union Bank
- And more...

### Extracted Information
- Transaction amount
- Transaction type (Credit/Debit)
- Account number (last 4 digits)
- Bank name
- Transaction date and time
- Available balance (if provided)
- Merchant/description

## ⚡ Performance Optimization

### Low-End Device Support
- Efficient database queries with indexing
- Lazy loading for large transaction lists
- Optimized layouts and view recycling
- Minimal memory footprint

### Battery Optimization
- Background tasks run only when necessary
- WorkManager for efficient scheduling
- Doze mode compatibility

## 🔒 Privacy & Security

- **Local Processing**: All data stays on device
- **No Internet Required**: Completely offline functionality
- **No Analytics**: No tracking or data collection
- **Secure Storage**: Encrypted database support (can be enabled)

## 🐛 Troubleshooting

### SMS Not Being Detected
1. Check SMS permissions are granted
2. Ensure SMS reading is enabled in Settings
3. Verify the SMS format matches supported banks

### Notifications Not Working
1. Grant notification permission
2. Check Settings > Enable Notifications
3. Verify notification channel is not blocked

### App Crashes
1. Clear app data
2. Reimport SMS history
3. Check Android version compatibility

## 📈 Future Enhancements

- [ ] Export data to CSV/Excel
- [ ] Backup and restore functionality
- [ ] Category-wise expense breakdown
- [ ] Budget planning tools
- [ ] Multi-currency support
- [ ] Widgets for quick overview
- [ ] Biometric authentication
- [ ] Cloud sync (optional)

## 🤝 Contributing

This is a personal project. For suggestions or issues, please create an issue in the repository.

## 📄 License

This project is for personal use. All rights reserved.

## 📞 Support

For issues or questions:
- Check the troubleshooting section
- Review the documentation
- Check permissions and settings

## 🙏 Acknowledgments

- Material Design Components by Google
- MPAndroidChart for graphs
- Room Persistence Library
- Kotlin Coroutines

---

**Version**: 1.0.0  
**Last Updated**: December 31, 2025  
**Min SDK**: 24 (Android 7.0)  
**Target SDK**: 34 (Android 14)
