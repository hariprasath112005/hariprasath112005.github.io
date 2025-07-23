---
title: "🩺 Emergency Assistance & Medicine Reminder App"
layout: post
author: hariprasath
lang: en
ref: 🩺 Emergency-Assistance-&-Medicine-Reminder-App
tag: projects
date: 2024-09-11 14:00:00 +0000
projects: true
summary: "A React Native-based emergency assist app that allows users to send live location, make SOS calls, and set medicine reminders, designed to aid elderly individuals."
category: project
---

# 🩺 Emergency Assistance & Medicine Reminder App

This is a **React Native** mobile application designed to assist users in emergencies and manage medicine reminders. It includes features like sending location, calling a set phone number, tracking medicine intake, and receiving spoken alerts via text-to-speech (TTS).

---

## 📱 Features

### 🆘 Emergency Utilities
- **Send Location** to a backend server with GPS coordinates.
- **Call Emergency Number** directly from the app.
- **Send SMS** (e.g., for "switching off" notifications) via backend integration.

### 💊 Medicine Reminder System
- Set **medicine name** and **reminder time**.
- Receive **daily reminders** with TTS voice prompts.
- Track **pill consumption**.
- Get alerts when **pill count is zero**.

### ☎️ Persistent Phone Number Storage
- Save phone number using `AsyncStorage`.
- Reuse stored number for emergency functions.

---

## 🚀 Getting Started

### 📦 Prerequisites

- Node.js ≥ 14.x
- React Native CLI or Expo CLI
- Android Studio or Xcode (for emulators or devices)
- A backend server ready to receive location and SMS data (`/api/send-location/`, `/api/switch_off/`)

### 📥 Installation

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
npm install
npx react-native link
```

## 📦 Required Packages

Ensure the following packages are installed (some may require native linking):

- `@react-native-community/geolocation`
- `@react-native-async-storage/async-storage`
- `react-native-tts`
- `axios`
- `react-native-permissions`
- `react-native-sound` *(optional for sound cues)*

---

## 📡 API Integration

You must have a backend server (e.g., Django, Flask, Node.js) listening at:

- `POST /api/send-location/` → Expects:
  ```json
  {
    "latitude": number,
    "longitude": number,
    "phone_number": string
  }
  ```

- `POST /api/switch_off/` → Expects:
```json
{
  "phone_number": string
}```


## Update the URLs in the code as necessary:

```bash
https://your-ngrok-url/api/send-location/
https://your-ngrok-url/api/switch_off/
```

## 📲 Running the App

### On Android:
```bash
npx react-native run-android
```

### On Ios:
```bash
npx react-native run-ios
```

## 🔒 Android Permissions

Add the following permissions to your `AndroidManifest.xml` file:

```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.CALL_PHONE" />
```

## 🎨 Screens Overview

- **HomeScreen**: Navigation hub for all features.
- **LocationScreen**: Send live location to the server.
- **CallScreen**: Call the emergency number.
- **PhoneNumberScreen**: Set and save contact number.
- **AddReminderScreen**: Configure medicine schedule and pill tracking.

---

## 🛠 Tech Stack

- React Native
- AsyncStorage
- React Native TTS
- Axios
- Geolocation API
- Linking API (for phone calls)

---

## 🧪 Testing Tips

- Use a real device for GPS and phone call features.
- Test medicine reminders by setting them for a minute or two ahead.
- Use [ngrok](https://ngrok.com/) or similar tools to expose local backend APIs to the app.
