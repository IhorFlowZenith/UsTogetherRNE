# 💕 UsTogether - Relationship Counter App

> **Every second counts when we are together. Let's start counting your beautiful story.**

A beautiful React Native mobile application that helps couples track and celebrate their relationship timeline. Count days, months, weeks, hours, minutes, and seconds together in one stunning app.

---

## 📱 Screenshots

### Onboarding Screen
Your journey begins here. A warm welcome with your relationship starting point.

![OnBoarding](OnBoarding.jpg)

### Home Screen
Real-time statistics of your relationship at a glance. See exactly how long you've been together in multiple time units.

![Home](Home.jpg)

### Calendar Screen
Visualize your entire relationship journey with our interactive calendar. Each heart represents a day together.

![Calendar](Calendar.jpg)

### Settings Screen
Set and customize your relationship start date. Input day, month, year, hour, and minute to the exact moment.

![Settings](Settings.jpg)

---

## 🎯 Features

### ✨ Core Features
- **Real-Time Counter** - Track days, months, weeks, hours, minutes, and seconds together
- **Interactive Calendar** - Beautiful calendar view with color-coded hearts showing your journey
- **Settings Management** - Set your exact relationship start date and time
- **Persistent Storage** - Data saved locally on your device using AsyncStorage
- **Responsive Design** - Works perfectly on all device sizes

### 💎 Premium UI/UX
- Gradient pink and coral color theme
- Smooth animations and transitions
- Heart icons for romantic touch
- Easy-to-read statistics cards
- Intuitive bottom navigation

---

## 📊 Home Screen Statistics

The home screen displays your relationship progress in multiple formats:

| Metric | Description |
|--------|-------------|
| **Days Together** | Total number of days since you met |
| **Months** | Full months passed in your relationship |
| **Weeks** | Total weeks together |
| **Total Hours** | Sum of all hours together |
| **Minutes** | Complete minutes counter |
| **Seconds** | Real-time seconds counter |

### Example (from screenshots)
```
Date: 17.08.2025
Days: 210
Months: 7
Weeks: 30
Hours: 5058
Minutes: 303520
Seconds: 18,211,243
```

---

## 📅 Calendar Feature

### How It Works
The calendar view displays every month from your relationship start date to today:

- **Red Hearts** ❤️ - Days you've been together
- **Empty Days** - Days before you met
- **Future Days** - Days that haven't happened yet

### Navigation
- Scroll through all months and years
- See your entire relationship timeline at once
- Track special milestones and anniversaries

---

## ⚙️ Settings

### Setting Your Start Date

The settings screen allows you to configure:

1. **Day** - Day of the month (1-31)
2. **Month** - Month of the year (1-12)
3. **Year** - Full year (e.g., 2025)
4. **Hour** - Hour of the day (0-23)
5. **Minute** - Minutes (0-59)

### Save Confirmation
After filling all fields, click **Save** to store your relationship start date securely on your device.

---

## 🛠️ Tech Stack

### Frontend
- **React Native** - Cross-platform mobile development
- **Expo** - React Native framework and tools
- **React Hooks** - useState, useEffect for state management
- **Ionicons** - Beautiful icon library for React Native

### Storage & Data
- **AsyncStorage** - Local device storage for persistent data
- **JavaScript Date API** - Date calculations and formatting
- **ISO 8601** - Standard date/time format (YYYY-MM-DDTHH:mm:ss)

### Styling
- **StyleSheet** - React Native styling API
- **Flexbox** - Responsive layout system
- **Custom Colors** - Coral (#E74C3C), Pink, Orange palette

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- Expo CLI (`npm install -g expo-cli`)
- A physical device or emulator

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ustogether.git
   cd ustogether
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Start the app**
   ```bash
   expo start
   ```

4. **Run on device**
   - Scan QR code with Expo Go app (iOS/Android)
   - Or run on emulator:
     ```bash
     # iOS
     expo start --ios
     
     # Android
     expo start --android
     ```

---

## 📁 Project Structure

```
UsTogether/
├── src/
│   ├── screens/
│   │   ├── OnBoardingScreen.js      # Welcome & introduction
│   │   ├── HomeScreen.js             # Statistics dashboard
│   │   ├── CalendarScreen.js         # Interactive calendar
│   │   └── SettingsScreen.js         # Date configuration
│   ├── components/
│   │   ├── MonthCard.js              # Single month calendar
│   │   ├── HeartDayItem.js           # Day with heart icon
│   │   └── StatCard.js               # Statistics card
│   ├── utils/
│   │   ├── dateCalculations.js       # Date math functions
│   │   └── storage.js                # AsyncStorage helpers
│   └── App.js                        # Main app component
├── assets/
│   ├── colors.js                     # Color constants
│   └── typography.js                 # Font styles
└── package.json
```

---

## 🧮 Key Calculations

### Days Together
```javascript
const daysPass = Math.floor((today - startDate) / (1000 * 60 * 60 * 24));
```

### Months (approximate)
```javascript
const months = (today.getFullYear() - startDate.getFullYear()) * 12 
             + (today.getMonth() - startDate.getMonth());
```

### Weeks
```javascript
const weeks = Math.floor(daysPass / 7);
```

### Hours
```javascript
const hours = daysPass * 24;
```

### Minutes
```javascript
const minutes = hours * 60;
```

### Seconds (Real-time)
```javascript
const seconds = (today - startDate) / 1000;
```

---

## 💾 Data Storage

The app uses **AsyncStorage** to persist your relationship start date:

```javascript
// Saving the date
const dateString = '2025-08-17T14:30:00';
await AsyncStorage.setItem('togetherDate', dateString);

// Loading the date
const saved = await AsyncStorage.getItem('togetherDate');
const startDate = new Date(saved);
```

### Data Format (ISO 8601)
```
2025-08-17T14:30:00
├─ YYYY: 2025 (year)
├─ MM: 08 (month)
├─ DD: 17 (day)
├─ T: separator
├─ HH: 14 (hour)
├─ mm: 30 (minutes)
└─ ss: 00 (seconds)
```

---

## 🎨 Design System

### Color Palette
- **Primary Red** - `#E74C3C` (Heart color, active state)
- **Background** - `#FFF5F0` (Soft coral/peach)
- **Card Background** - `rgba(255, 255, 255, 0.6)` (Semi-transparent white)
- **Text Primary** - `#333333` (Dark gray)
- **Text Secondary** - `#E8856A` (Coral/salmon)
- **Accent Orange** - `#FFD4C4` (Light peachy)

### Typography
- **Headers** - Bold, 24-28px
- **Titles** - SemiBold, 18-20px
- **Body** - Regular, 14-16px
- **Labels** - Regular, 12-14px

### Spacing
- **Card Padding** - 16px
- **Container Padding** - 16px
- **Gap Between Elements** - 8-12px
- **Border Radius** - 12-32px

---

## 🔧 Customization

### Changing Colors
Edit the color constants in your stylesheet:

```javascript
const styles = StyleSheet.create({
  heartContainer: {
    // Change the heart color
    // Default: #E74C3C (red)
  },
  container: {
    // Change background
    // Default: light peach
  },
});
```

### Modifying Date Format
Change the ISO 8601 format in `dateString` creation:

```javascript
// Current format: YYYY-MM-DDTHH:mm:ss
const dateString = `${year}-${month.padStart(2, '0')}-${day.padStart(2, '0')}T${hour.padStart(2, '0')}:${minute.padStart(2, '0')}:00`;

// You can modify to include seconds, timezone, etc.
```

---

## 📈 Future Enhancements

Potential features for future versions:

- [ ] **Notifications** - Anniversary and milestone reminders
- [ ] **Photo Gallery** - Store and display couple photos
- [ ] **Timeline Events** - Mark special dates (anniversaries, trips, etc.)
- [ ] **Sharing** - Share your counter with friends
- [ ] **Dark Mode** - Dark theme support
- [ ] **Cloud Sync** - Sync data across devices
- [ ] **Themes** - Different color schemes
- [ ] **Multiple Relationships** - Track multiple counters
- [ ] **Statistics** - Graphs and charts of your journey
- [ ] **Social Media Integration** - Share milestones on Instagram/TikTok

---

## 🐛 Known Issues & Limitations

- Currently stores date locally only (no cloud backup)
- No offline-first sync mechanism
- Real-time seconds counter updates on app focus (not in background)
- Limited to single relationship tracking

---

## 📝 Code Examples

### Creating the Date String
```javascript
const saveDate = async (): Promise<void> => {
  if (!day || !month || !year || !hour || !minute) {
    Alert.alert('Error', 'Please fill all fields');
    return;
  }

  const dateString = `${year}-${month.padStart(2, '0')}-${day.padStart(2, '0')}T${hour.padStart(2, '0')}:${minute.padStart(2, '0')}:00`;
  
  await AsyncStorage.setItem('togetherDate', dateString);
  Alert.alert('Success', 'Date saved! 💕');
};
```

### Calculating Days Together
```javascript
const calculateDaysTogether = (startDate: Date): number => {
  const today = new Date();
  const timePass = today.getTime() - startDate.getTime();
  return Math.floor(timePass / (1000 * 60 * 60 * 24));
};
```

### Heart Color Logic
```javascript
const getHeartColor = (currentDate: Date, startDate: Date, today: Date): string => {
  const isLovePeriod = currentDate >= startDate && currentDate <= today;
  const isBeforeTogether = currentDate < startDate;

  if (isLovePeriod) return '#E74C3C';      // Red heart
  if (isBeforeTogether) return '#DDD';     // Gray (before met)
  return '#FFD4C4';                        // Peach (future)
};
```

---

## 🤝 Contributing

We love contributions! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 💌 About

**UsTogether** was created with ❤️ to help couples celebrate and visualize their love story. Every day together is special, and we wanted to create an app that honors that.

---


## 🙏 Acknowledgments

- Built with **React Native** and **Expo**
- Icons from **Ionicons**
- Inspired by love and beautiful design