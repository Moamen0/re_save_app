<div align="center">

# ♻️ ReSave

### Smart Recycling & Waste Management Platform

**Connecting users, riders, and recycling factories to make sustainable living simple, measurable, and rewarding.**

![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)

<p>
  <a href="#-key-features">Features</a> •
  <a href="#-screenshots">Screenshots</a> •
  <a href="#-tech-stack">Tech Stack</a> •
  <a href="#-architecture--engineering-decisions">Architecture</a> •
  <a href="#-getting-started">Getting Started</a> •
  <a href="#-contributing">Contributing</a>
</p>

</div>

---

## 📖 Table of Contents

- [About ReSave](#-about-resave)
- [Key Features](#-key-features)
- [Screenshots](#-screenshots)
- [Tech Stack](#-tech-stack)
- [Architecture & Engineering Decisions](#-architecture--engineering-decisions)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Learning Outcomes](#-learning-outcomes)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)
- [Developer](#-developer)

---

## 🌍 About ReSave

**ReSave** is a smart recycling and waste management platform built with Flutter, designed to make recycling accessible, transparent, and genuinely rewarding. The platform connects three key participants in the recycling lifecycle — **users**, **riders**, and **recycling factories** — into a single streamlined experience.

Rather than treating recycling as a one-off chore, ReSave is built around a simple insight: **people recycle more when they can see the impact of what they recycle.** Users can browse recyclable categories, add items for pickup, manage recycling requests, and track exactly how their actions translate into environmental impact — from sustainability percentages to completed challenges and long-term contribution history.

This repository contains the **customer-facing mobile application**, the primary entry point into the ReSave platform, built with modern Flutter engineering practices and a strong emphasis on scalability, maintainability, and clean architecture. It communicates with a dedicated Laravel REST API and is part of a broader ecosystem that also includes a companion rider application for logistics and pickup fulfillment.

> ReSave isn't just an app that lets you recycle — it's an app that shows you *why it matters*.

---

## ✨ Key Features

### 🔐 Authentication
Secure, session-aware authentication built for a smooth first-time and returning-user experience.
- Email-based login and registration
- Persistent sessions — users stay signed in across app restarts
- Full profile management (view and update personal information)

### ♻️ Recycling
The core recycling workflow, designed to make submitting recyclables effortless.
- Browse all supported recyclable categories at a glance
- Add recyclable items with details before requesting pickup
- Create, track, and manage recycling requests end-to-end

### 🛒 Cart
A familiar, e-commerce-grade cart experience applied to recycling submissions.
- Add items to the cart before finalizing a recycling request
- Remove items or adjust quantities inline
- A dedicated empty-cart state that gently guides users back to browsing

### 🗂️ Categories
Recyclable materials are organized into clear, browsable categories — including common groups such as **plastics, paper & cardboard, glass, metals, and electronics** — so users always know exactly what they can submit and where it belongs.

### 🗺️ Google Maps & Location
Location-aware from the ground up, so pickups and deliveries always land in the right place.
- Automatic detection of the user's current location
- Interactive Google Maps view for selecting a precise pickup/delivery point
- Careful, user-respecting handling of **runtime location permissions** — including graceful fallback states when access is denied

> 📍 Implementing runtime location permissions correctly — across both Android and iOS permission models — was one of the most valuable engineering challenges tackled during development, ensuring the app degrades gracefully rather than breaking when permissions are limited or revoked.

### 🔔 Push Notifications
Real-time engagement powered by Firebase Cloud Messaging (FCM).
- Runtime notification permission handling
- Push notifications for request status updates and platform activity
- An in-app notification center for reviewing past alerts
- Real-time updates without requiring a manual refresh

> 🔔 Integrating FCM end-to-end — from requesting notification permissions to reliably delivering and displaying real-time updates — was another significant learning experience, particularly around token lifecycle management and cross-platform notification behavior.

### 📊 Environmental Impact
The feature at the heart of ReSave's mission. Instead of a static "thank you," users get a living dashboard of their contribution:
- Personal environmental impact tracking
- Cumulative recycling contribution over time
- A sustainability progress percentage
- Visual progress toward personal recycling goals

By turning an abstract action (recycling) into a concrete, visible outcome, this feature is designed to keep users motivated and coming back.

### 🏆 Challenges
Gamified challenges encourage users to build recycling into a habit rather than a one-time action, rewarding consistency and turning sustainability into an ongoing, engaging journey rather than a single transaction.

### 🤖 AI
ReSave incorporates AI-assisted identification and classification of recyclable waste, helping users quickly determine what category an item belongs to. This reduces user error, speeds up the item-submission flow, and improves the overall accuracy of what enters the recycling pipeline.

### 🌐 Localization
Built for a genuinely multilingual, multi-directional audience from day one.
- Full English localization
- Full Arabic localization
- Complete **RTL (right-to-left)** layout support

### 🎨 Theme
- Light mode
- Dark mode
- Consistent design language across both

---

## 📱 Screenshots

<div align="center">

<table>
  <tr>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/splash_screen.png?raw=true" width="200"/><br/><sub><b>Splash</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/login_screen.png?raw=true" width="200"/><br/><sub><b>Login</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/home_page.png?raw=true" width="200"/><br/><sub><b>Home</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/categories_page.png?raw=true" width="200"/><br/><sub><b>Categories</b></sub></td>
  </tr>
  <tr>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/add_item_page.png?raw=true" width="200"/><br/><sub><b>Add Item</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/cart_page.png?raw=true" width="200"/><br/><sub><b>Cart</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/empty_cart_screen.png?raw=true" width="200"/><br/><sub><b>Empty Cart</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/map_page.png?raw=true" width="200"/><br/><sub><b>Map</b></sub></td>
  </tr>
  <tr>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/location_access_permission.png?raw=true" width="200"/><br/><sub><b>Location Permission</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/nottifaction_screen.png?raw=true" width="200"/><br/><sub><b>Notifications</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/challenges_page.png?raw=true" width="200"/><br/><sub><b>Challenges</b></sub></td>
    <td align="center"><img src="https://github.com/yasen-edres/re_save_app/blob/master/profile_page.png?raw=true" width="200"/><br/><sub><b>Profile</b></sub></td>
  </tr>
</table>

</div>

---

## 🛠️ Tech Stack

<div align="center">

![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)
![Bloc](https://img.shields.io/badge/State_Management-Bloc%20%2F%20Cubit-13B9FD?style=for-the-badge)
![GetIt](https://img.shields.io/badge/DI-GetIt-4CAF50?style=for-the-badge)
![Injectable](https://img.shields.io/badge/DI-Injectable-4CAF50?style=for-the-badge)
![Dio](https://img.shields.io/badge/Networking-Dio-0175C2?style=for-the-badge)
![Retrofit](https://img.shields.io/badge/Networking-Retrofit-48B983?style=for-the-badge)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![FCM](https://img.shields.io/badge/Firebase_Cloud_Messaging-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Google Maps](https://img.shields.io/badge/Google_Maps-4285F4?style=for-the-badge&logo=googlemaps&logoColor=white)

</div>

| Layer | Technologies |
|---|---|
| **Mobile** | Flutter, Dart |
| **Architecture** | Clean Architecture, MVVM, Repository Pattern |
| **State Management** | `flutter_bloc` (Cubit) |
| **Dependency Injection** | GetIt, Injectable |
| **Networking** | Dio, Retrofit, `json_serializable` |
| **Backend** | Laravel REST API (Sanctum authentication), MySQL |
| **Firebase** | Firebase Authentication, Firebase Cloud Messaging (FCM) |
| **Maps & Location** | Google Maps, Geolocator, runtime location services |
| **Local Storage** | Shared Preferences |
| **Other** | Permission Handler, Cached Network Image, Image Picker, Intl |

---

## 🏗️ Architecture & Engineering Decisions

ReSave isn't just "using Flutter" — it's engineered around a deliberate set of architectural decisions chosen to keep the codebase scalable, testable, and maintainable as the platform grows across the user app, rider app, and backend.

<details open>
<summary><b>Why Clean Architecture?</b></summary>
<br>

Clean Architecture separates the codebase into independent **Presentation**, **Domain**, and **Data** layers, so core business rules never depend on Flutter widgets, third-party SDKs, or how data happens to be fetched. Domain entities stay pure and framework-agnostic, while DTOs handle the messy work of mapping raw API responses into clean domain models. The payoff: features can be tested, replaced, or extended without ever touching unrelated layers.
</details>

<details open>
<summary><b>Why MVVM?</b></summary>
<br>

MVVM enforces a strict separation between "what the screen renders" and "how the screen behaves." Views stay declarative and dumb; a ViewModel (implemented via Cubit) owns all presentation logic and exposes simple, observable state. This makes UI code easier to reason about, easier to test in isolation, and far less prone to logic creeping into widgets.
</details>

<details open>
<summary><b>Why Repository Pattern?</b></summary>
<br>

The Repository Pattern abstracts every data source — the Laravel REST API, local cache, device storage — behind a single, consistent interface consumed by the domain layer. Use cases never need to know *where* data comes from, only *what* it represents. This keeps business logic fully decoupled from implementation details and makes it trivial to swap, mock, or extend data sources later.
</details>

<details open>
<summary><b>Why Dependency Injection (GetIt + Injectable)?</b></summary>
<br>

GetIt provides a lightweight service locator, while Injectable generates the registration boilerplate at compile time via code generation. Together they produce a scalable, explicit dependency graph with zero manual wiring — reducing human error and making every dependency trivially mockable in tests.
</details>

<details open>
<summary><b>Why Bloc (Cubit)?</b></summary>
<br>

Cubit delivers predictable, unidirectional state management with far less ceremony than a full event-based Bloc implementation, while still keeping business logic completely out of the widget tree. Every state transition is explicit, testable in isolation, and easy to trace — which matters as the number of screens and states grows.
</details>

<details open>
<summary><b>Why Dio + Retrofit?</b></summary>
<br>

Dio provides a full-featured HTTP client — interceptors, timeouts, structured error handling — while Retrofit generates strongly-typed API service definitions at compile time, paired with `json_serializable` for model (de)serialization. Together, they eliminate manual JSON parsing, catch API contract mismatches at compile time rather than at runtime, and keep networking code declarative and consistent across the app.
</details>

Together, these decisions give ReSave a foundation that prioritizes:

- **Scalability** — new features slot into the existing feature-first structure without disturbing unrelated code
- **Maintainability** — clear boundaries mean changes stay localized
- **Separation of Concerns** — UI, business logic, and data access never bleed into one another
- **Testability** — every layer can be tested independently, with dependencies swapped via DI
- **Modularity** — each feature is a self-contained vertical slice, from UI down to data source

---

## 📂 Project Structure

ReSave follows a **Feature-First** organization built on top of Clean Architecture, keeping every feature self-contained across its own data, domain, and presentation layers.

```
lib/
├── core/
│   ├── di/                       # GetIt + Injectable setup
│   │   ├── injection.dart
│   │   └── injection.config.dart
│   ├── network/                  # Dio client, interceptors, API result wrappers
│   │   ├── dio_factory.dart
│   │   ├── api_result.dart
│   │   └── network_info.dart
│   ├── error/                    # Exceptions & failure types
│   │   ├── exceptions.dart
│   │   └── failures.dart
│   ├── routing/                  # App-wide navigation
│   │   ├── app_router.dart
│   │   └── routes.dart
│   ├── theme/                    # Light / dark theming
│   │   ├── app_colors.dart
│   │   ├── app_text_styles.dart
│   │   └── app_theme.dart
│   ├── localization/             # English / Arabic + RTL
│   └── widgets/                  # Shared, reusable UI components
│
├── features/
│   ├── auth/
│   │   ├── data/
│   │   │   ├── datasources/
│   │   │   ├── models/
│   │   │   └── repositories/
│   │   ├── domain/
│   │   │   ├── entities/
│   │   │   ├── repositories/
│   │   │   └── usecases/
│   │   └── presentation/
│   │       ├── cubit/
│   │       ├── screens/
│   │       └── widgets/
│   │
│   ├── home/
│   ├── categories/
│   ├── recycling_requests/
│   ├── cart/
│   ├── map/
│   ├── notifications/
│   ├── environmental_impact/
│   ├── challenges/
│   └── profile/
│       └── (each follows the same data / domain / presentation structure)
│
├── generated/                    # Localization-generated files
└── main.dart
```

Every feature mirrors the same three-layer structure, so once you understand one feature, you understand them all.

---

## 🚀 Getting Started

### Prerequisites

- Flutter SDK (stable channel)
- Dart SDK
- Android Studio / Xcode for platform builds
- A Firebase project (for Authentication + FCM)
- A Google Maps API key
- A running instance of the ReSave Laravel backend API (see [@yasen-edres](https://github.com/yasen-edres) for related repositories)

### Installation

<details>
<summary><b>Click to expand full setup steps</b></summary>
<br>

**1. Clone the repository**
```bash
git clone https://github.com/yasen-edres/re_save_app.git
cd re_save_app
```

**2. Install dependencies**
```bash
flutter pub get
```

**3. Generate code**

Required for Injectable, Retrofit, and `json_serializable` generated files:
```bash
flutter pub run build_runner build --delete-conflicting-outputs
```

**4. Configure Firebase**

- Create a Firebase project and enable **Authentication** and **Cloud Messaging**
- Add `google-services.json` to `android/app/`
- Add `GoogleService-Info.plist` to `ios/Runner/`
- Or configure via the FlutterFire CLI:
```bash
flutterfire configure
```

**5. Configure Google Maps**

- Enable the Maps SDK for Android/iOS in the Google Cloud Console
- Add your API key to `android/app/src/main/AndroidManifest.xml` and `ios/Runner/AppDelegate.swift`

**6. Configure the Laravel backend connection**

- Point the app's base API URL to your running Laravel backend instance
- Ensure the backend's MySQL database is configured and migrated

**7. Run the application**
```bash
flutter run
```

</details>

---

## 📚 Learning Outcomes

Building ReSave was as much an engineering exercise as a product one. Key takeaways from the project include:

- Structuring a real Flutter application around **Clean Architecture**, **MVVM**, and the **Repository Pattern**
- Designing a scalable **dependency injection** graph with GetIt and Injectable
- Managing complex UI state predictably with **Bloc/Cubit**
- Consuming and integrating **REST APIs** with Dio and Retrofit against a real **Laravel** backend
- Implementing **Firebase Authentication** and **Firebase Cloud Messaging** end-to-end
- Working with **Google Maps** and handling **runtime permissions** gracefully across platforms
- Building genuinely **scalable, maintainable Flutter applications** rather than single-screen prototypes
- Applying **real-world software architecture** decisions and understanding their trade-offs firsthand

---

## 🤝 Contributing

Contributions are welcome and appreciated. To contribute:

1. **Fork** the repository
2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Commit your changes** with clear, descriptive messages
   ```bash
   git commit -m "feat: add your feature description"
   ```
4. **Push to your branch**
   ```bash
   git push origin feature/your-feature-name
   ```
5. **Open a Pull Request** describing what you changed and why

Please keep pull requests focused — smaller, well-scoped PRs are easier to review and merge.

---

## 📄 License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2026 Yasen Edres

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📬 Contact

Questions, feedback, or collaboration ideas are always welcome — the best way to reach out is by opening an issue on GitHub or connecting directly:

- **GitHub:** [@yasen-edres](https://github.com/yasen-edres)

---

## 👨‍💻 Developer

<div align="center">

**Yasen Edres**
*Flutter Developer*

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/yasen-edres)

</div>

---

<div align="center">

If ReSave inspired you or helped you learn something, consider giving the repository a ⭐ — it helps others discover the project.

**Made with 💚 for a more sustainable future.**

</div>
