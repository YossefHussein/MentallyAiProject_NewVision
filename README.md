# Mentally AI

Mentally AI is a complete mental wellness application that combines a Node.js/Express backend with a Flutter mobile app. The platform helps users improve their emotional well-being by providing mood-based guidance, daily quotes, calming music, meditation resources, and a more supportive wellness experience.

This repository contains both the backend API and the mobile app in one project.

## Overview

The app is designed to support people who want to:
- understand their mood and emotional state;
- receive daily inspiration and guidance;
- listen to relaxing music;
- explore meditation classes;
- access support resources in a user-friendly mobile experience.

## Features

### Backend features
- Express REST API with CORS and rate limiting
- AI-powered mood and wellness advice using Gemini
- Daily quote generation
- Mood-based advice endpoint
- Song catalog endpoint
- Meditation class catalog endpoint
- PostgreSQL/Neon database integration
- Environment-based configuration for secure credentials

### Mobile app features
- Flutter-based user interface
- Authentication screens and app onboarding
- Mood tracking with emotional buttons
- Daily quote section
- Personalized mood advice and notifications
- AI-assisted emotional guidance flow
- Music playlist screen
- Meditation screen and mental wellness dashboard
- Mood chart/history support
- Multiple language support: English and Arabic
- Firebase integration for auth, crash analytics, and app services
- Google Ads support
- Local notifications and permission handling
- Splash screen customization

## Project structure

```text
MentallyAiProject_NewVision/
├── backend/
│   ├── adapters/
│   ├── application/
│   ├── domain/
│   ├── infrastructure/
│   ├── .env.example
│   ├── app.js
│   ├── package.json
│   └── package-lock.json
├── mobile/
│   ├── lib/
│   ├── assets/
│   ├── android/
│   ├── ios/
│   ├── web/
│   ├── env.example
│   ├── pubspec.yaml
│   └── README.md
├── LICENSE
├── README.md
└── .gitignore
```

## Backend API

The backend exposes the following endpoints:

| Endpoint | Method | Description |
| --- | --- | --- |
| `/meditation/dailyQuote` | GET | Returns a daily quote |
| `/meditation/myMood/:mood` | GET | Returns advice based on the user mood |
| `/songs/all` | GET | Returns all songs |
| `/meditationClasses/allClasses` | GET | Returns meditation classes |

## Tech stack

### Backend
- Node.js
- Express.js
- PostgreSQL
- Gemini AI integration
- dotenv
- CORS
- express-rate-limit

### Mobile app
- Flutter
- Dart
- Firebase Auth
- Firebase Crashlytics
- easy_localization
- go_router
- flutter_bloc
- SQLite
- Google Mobile Ads
- flutter_local_notifications
- syncfusion_flutter_charts / fl_chart

## Setup and installation

### 1) Backend setup

Open the backend folder:

```bash
cd backend
npm install
cp .env.example .env
```

Then update the `.env` file with your real values:

```env
PORT=6000
Gemini_API_KEY=YourGeminiApiKey
pgUser=YourPostgresUser
pgPassword=YourPassword
pgHost=YourPostgresHost
pgPort=5432
pgDataBase=YourPostgresNameOfDatabase
```

Run the backend:

```bash
npm run dev
```

Or in production mode:

```bash
npm start
```

### 2) Mobile app setup

Open the mobile folder:

```bash
cd mobile
flutter pub get
cp env.example .env
```

Add the backend IP address in the mobile `.env` file:

```env
IpServer=192.168.1.10
```

> Use the machine IP where the backend is running, especially when testing on a real Android device.

Generate localization files:

```bash
flutter pub run easy_localization:generate -S "assets/translations" -O "lib/translations"
flutter pub run easy_localization:generate -S "assets/translations" -O "lib/translations" -o "locale_keys.dart" -f keys
```

Run the app:

```bash
flutter run
```

For release mode:

```bash
flutter run --release
```

## Android / Gradle notes

If you encounter Gradle issues on your machine, use Java JDK 21.

```bash
./gradlew clean build
```

## Splash screen

To generate or update the native splash screen:

```bash
flutter pub run flutter_native_splash:create
```

## Useful notes

- The backend and mobile app should be on the same network when testing with a real device.
- Make sure your PostgreSQL database is running and the credentials in `.env` are correct.
- If your app is using Firebase, ensure the Firebase configuration files are set correctly in the mobile project.

## License

This project is licensed under the MIT License.

## Future improvements

Possible future enhancements include:
- user accounts and saved mood history;
- chat with AI wellness assistant;
- personalized recommendations based on user behavior;
- premium content for meditation and therapy plans;
- improved analytics and dashboards.

