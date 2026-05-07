# RESUMETRACKERAP

[![Flutter](https://img.shields.io/badge/Flutter-3.32.0-blue?logo=flutter)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.8.0-blue?logo=dart)](https://dart.dev)
[![Riverpod](https://img.shields.io/badge/State-Riverpod-purple)](https://riverpod.dev)
[![Hive](https://img.shields.io/badge/Storage-Hive-orange)](https://pub.dev/packages/hive)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A feature-rich, **offline-first** Flutter mobile application for building professional resumes and tracking job applications throughout your career journey. Built with **clean architecture**, **Material 3 UI**, and **Riverpod state management**.

---

## ✨ Features

### 📄 Resume Builder
- Create, edit, delete multiple resumes
- Dynamic add/remove entries for Education, Skills & Experience
- Personal details: name, email, phone

### 💼 Job Application Tracker
- Track applications to any company with company name, role, date, notes
- Auto-generated unique Application ID (UUID v4)
- Link a saved resume to each application
- Full-featured create & edit forms

### 📊 Dashboard
- Total application count at a glance
- Status-wise stat cards + counts
- Interactive **PieChart** (fl_chart) with percentage breakdown
- Recent 5 applications list with greeted header

### 🔄 Application Status Tracking
| Status | Color |
|---|---|
| ✉️ Applied | Blue |
| 🔖 Shortlisted | Amber |
| 📅 Interview Scheduled | Purple |
| ❌ Rejected | Red |
| ✅ Selected | Green |

Dynamic one-tap status updates from the details screen.

### 🔍 Search & Filter
- Real-time search by company name or role
- Filter by any status (All / Applied / Shortlisted / etc.)
- Sort by newest or oldest date

### 📡 Offline-First
- **100% offline** — works without internet
- Hive persists all data locally
- Automatic sync queue; syncs to Firebase when network restores
- Connectivity badge in Dashboard app bar

### 🌗 Dark Mode
- Follows system theme (light / dark)
- Material 3 color scheme with Poppins typography

---

## 📂 Folder Structure

```
lib/
├── main.dart                    # App entry, Hive init, ProviderScope
├── models/
│   ├── resume_model.dart        # Hive TypeAdapter (typeId: 0)
│   ├── resume_model.g.dart      # Hand-written TypeAdapter
│   ├── job_application_model.dart  # Hive TypeAdapter (typeId: 1)
│   ├── job_application_model.g.dart
│   └── application_status.dart # Enum + color/icon/label extensions
├── providers/
│   ├── resume_provider.dart
│   ├── job_application_provider.dart
│   ├── dashboard_provider.dart
│   ├── search_filter_provider.dart
│   └── connectivity_provider.dart
├── services/
│   └── sync_service.dart        # Connectivity + Firebase stub
├── database/
│   ├── hive_service.dart        # Singleton CRUD service
│   └── dummy_data.dart          # Seed data (3 resumes, 8 applications)
├── screens/
│   ├── splash_screen.dart
│   ├── main_shell.dart          # Bottom NavigationBar
│   ├── dashboard_screen.dart
│   ├── resume_list_screen.dart
│   ├── resume_builder_screen.dart
│   ├── applications_list_screen.dart
│   ├── job_application_entry_screen.dart
│   ├── application_details_screen.dart
│   └── search_filter_screen.dart
├── widgets/
│   ├── status_badge.dart
│   ├── resume_card.dart
│   ├── application_card.dart
│   ├── empty_state_widget.dart
│   ├── custom_text_field.dart
│   └── section_header.dart
└── utils/
    ├── app_theme.dart           # Material 3 light + dark themes
    ├── constants.dart
    ├── validators.dart
    ├── date_formatter.dart
    └── id_generator.dart
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Flutter 3.32 | UI framework |
| Riverpod | State management |
| Hive + Hive Flutter | Offline local storage |
| fl_chart | Dashboard pie chart |
| flutter_animate | Micro-animations |
| connectivity_plus | Network detection |
| google_fonts (Poppins) | Typography |
| uuid | Unique ID generation |
| intl | Date formatting |

---

## 🚀 Getting Started

### Prerequisites
- Flutter SDK ≥ 3.0.0
- Android Studio / VS Code with Flutter extension

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/smart_resume_builder.git
cd smart_resume_builder

# 2. Install dependencies
flutter pub get

# 3. Run the app (debug mode)
flutter run

# 4. Build release APK
flutter build apk --release
```

---

## 🔁 Commit Stages

| Stage | Description |
|---|---|
| **1. Project Initialization** | `flutter create`, `pubspec.yaml`, folder structure, themes |
| **2. UI Implementation** | All screens, widgets, navigation shell |
| **3. Resume + Tracking Logic** | Models, TypeAdapters, Providers, CRUD operations |
| **4. Offline Storage + Enhancements** | Hive integration, seed data, sync service, animations |

---

## 🔮 Extending with Firebase

The `SyncService` includes a stub ready for Firebase integration:

1. Add `firebase_core` and `cloud_firestore` to `pubspec.yaml`
2. Run `flutterfire configure`
3. Uncomment the Firestore write in `lib/services/sync_service.dart`

---

## 📝 License

MIT License — see [LICENSE](LICENSE) for details.
