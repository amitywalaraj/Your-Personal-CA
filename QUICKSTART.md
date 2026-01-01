# 🚀 Quick Start Guide - Expense Tracker

## ⚡ Get Started in 5 Minutes

### Prerequisites
- Windows PC
- Android Studio installed
- Android device or emulator

### Step 1: Open Project (1 minute)
1. Launch Android Studio
2. Click "Open"
3. Navigate to: `C:\Users\Dev-Raj\Downloads\App`
4. Click "OK"
5. Wait for Gradle sync to complete

### Step 2: Build Project (2 minutes)
```
In Android Studio:
- Click Build > Make Project
- Wait for build to complete
- Check for any errors in Build tab
```

### Step 3: Run App (2 minutes)
1. Connect Android phone via USB (enable USB debugging)
   OR
   Start Android emulator
2. Click the green Run button (▶️)
3. Select your device
4. Wait for installation

### Step 4: First Launch
1. Grant SMS permissions when prompted
2. Grant notification permissions
3. Go to Settings tab
4. Click "Import SMS History"
5. Return to Dashboard to view data

## 🎯 What to Expect

### Dashboard Screen
- Financial Year summary card (purple)
- Today's transactions
- This week's summary
- This month's summary
- Recent transactions list

### Transactions Screen
- All transactions in chronological order
- Green amounts = Money received (Credit)
- Red amounts = Money spent (Debit)
- FAB button (+) to add manual transaction

### Settings Screen
- SMS reading toggle
- Import SMS button
- Transaction limits section
- Reminders section
- Notifications toggle

## 🧪 Test the App

### Option 1: Import Real SMS
1. Go to Settings
2. Click "Import SMS History"
3. Wait for import to complete
4. View transactions on Dashboard

### Option 2: Send Test SMS
Send this SMS to your device:
```
Your A/c XX1234 debited by Rs.500.00 on 31-Dec-25. Avbl Bal:Rs.10000.00
```

The app should automatically detect and parse it!

## 🐛 Troubleshooting

### Build Failed?
```powershell
# Clean and rebuild
cd "C:\Users\Dev-Raj\Downloads\App"
gradlew clean
gradlew build
```

### Gradle Sync Issues?
```
File > Invalidate Caches > Invalidate and Restart
```

### App Not Installing?
```powershell
# Check device connection
adb devices

# If no devices, enable USB debugging on phone
# Settings > Developer Options > USB Debugging
```

### No Transactions Showing?
1. Check SMS permissions are granted
2. Ensure SMS reading is enabled in Settings
3. Import SMS history manually
4. Check you have bank transaction SMS

### Permissions Denied?
1. Go to phone Settings
2. Apps > Expense Tracker
3. Permissions
4. Enable SMS and Notifications

## 📱 Using the App

### Set Your First Limit
1. Go to Settings
2. Scroll to "Transaction Limits"
3. Click "Add"
4. Choose Daily
5. Enter ₹5000
6. Save

### Create a Reminder
1. Go to Settings
2. Scroll to "Reminders"
3. Click "Add"
4. Enter ₹50000 threshold
5. Choose Daily frequency
6. Save

### View Financial Year Data
1. Go to Dashboard
2. Top card shows FY summary
3. Shows total credit and debit
4. Automatically calculates Apr-Mar

## 🎨 Customization

### Change Colors
Edit: `app/src/main/res/values/colors.xml`

### Change App Name
Edit: `app/src/main/res/values/strings.xml`
```xml
<string name="app_name">My Expense App</string>
```

### Change App Icon
Replace: `app/src/main/res/mipmap/ic_launcher.png`

## 📊 Understanding the Data

### Transaction Colors
- 🟢 Green = Money IN (Credit)
- 🔴 Red = Money OUT (Debit)

### Period Summaries
- **Today**: Last 24 hours
- **This Week**: Last 7 days
- **This Month**: Current calendar month
- **Financial Year**: April to March

### Account Numbers
Shows last 4 digits for security (e.g., ****1234)

## 🔔 Notifications

### When You'll Get Notified
1. When spending reaches 80% of limit
2. When reminder threshold is crossed
3. Optional: On every new transaction

### Managing Notifications
- Settings > Enable Notifications toggle
- Phone Settings > Apps > Expense Tracker > Notifications

## 💾 Data Management

### Where is Data Stored?
- Local SQLite database
- Location: `/data/data/com.expensetracker.app/databases/`
- No cloud, no internet needed

### Import SMS History
- Imports last 90 days
- Parses bank transaction messages only
- Shows progress and count

### Data Safety
- All data stays on device
- No sharing with third parties
- No analytics or tracking

## 🎓 Next Steps

### Learn More
1. Read [README.md](README.md) for full documentation
2. Check [FEATURES.md](FEATURES.md) for all features
3. Review [BUILD.md](BUILD.md) for advanced building

### Customize
1. Add your bank patterns to `SmsParser.kt`
2. Customize colors and themes
3. Add new features

### Share
1. Build release APK
2. Share with friends/family
3. Or publish to Play Store!

## 📞 Need Help?

### Common Issues
1. **No permissions**: Grant in phone settings
2. **No transactions**: Import SMS or send test SMS
3. **App crashes**: Check Android version (need 7.0+)
4. **Build errors**: Clean and rebuild project

### Logs
View detailed logs:
```powershell
adb logcat | Select-String "ExpenseTracker"
```

## ✅ Success Checklist

After setup, you should have:
- ✅ App installed and running
- ✅ SMS permissions granted
- ✅ Transactions visible on dashboard
- ✅ Limits and reminders configured
- ✅ Notifications working

---

**🎉 You're all set! Start tracking your expenses smartly!**

Time to complete setup: **5 minutes**  
Difficulty: **Easy** ⭐⭐☆☆☆

For detailed documentation, see [README.md](README.md)
