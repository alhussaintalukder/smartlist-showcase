<p align="center"><img src="screenshots/logo.png" width="96" alt="SmartList logo"></p>
<h1 align="center">SmartList</h1>
<p align="center"><b>Plan, track and analyse shopping and shared expenses, together.</b></p>
<p align="center">
  <a href="https://play.google.com/store/apps/details?id=com.alhussain.smartlist"><img src="https://img.shields.io/badge/Get%20it%20on-Google%20Play-34A853?logo=googleplay&logoColor=white" alt="Get it on Google Play"></a>
  <img src="https://img.shields.io/badge/React%20Native-Expo-61DAFB?logo=react&logoColor=black" alt="React Native">
  <img src="https://img.shields.io/badge/Spring%20Boot-Java%2021-6DB33F?logo=springboot&logoColor=white" alt="Spring Boot">
  <img src="https://img.shields.io/badge/Oracle%20Cloud-Docker-F80000?logo=oracle&logoColor=white" alt="Oracle Cloud">
</p>

> Showcase repository. The source code is private; this page covers the product, its architecture and the engineering behind it.
> Built solo by [Md. Al Hussain Talukder](https://github.com/alhussaintalukder) · Al Hussain Smart Solution

---

## 📱 Screenshots

<p align="center">
  <img src="screenshots/SmartList-1-HomeScreen.png" width="200" alt="Home">
  <img src="screenshots/SmartList-2-Organize.png" width="200" alt="Organize">
  <img src="screenshots/SmartList-3-entry.png" width="200" alt="Quick entry">
  <img src="screenshots/SmartList-4-track.png" width="200" alt="Track">
</p>
<p align="center">
  <img src="screenshots/SmartList-5-analyze.png" width="200" alt="Analyze">
  <img src="screenshots/SmartList-6-collaborate.png" width="200" alt="Collaborate">
  <img src="screenshots/SmartList-7-prices.png" width="200" alt="Prices">
  <img src="screenshots/SmartList-8-theme.png" width="200" alt="Themes">
</p>

## 💡 Why SmartList
It started with 14 housemates sharing groceries and bills in spreadsheets, which led to confusion and disputes. In South Asia, many families also settle shop bills monthly rather than per purchase. SmartList brings lists, expenses, shops and analytics into one collaborative app.

## ✨ Features
- 🌳 **Tree organisation:** Groups → Lists → Sub-lists → Items
- 👥 **Real-time collaboration:** share groups with family, roommates or teams, with admin and member roles, synced instantly over WebSocket
- 📊 **Analytics:** price trends, budget forecasting, spending by category, item, buyer or period
- 🧾 **Receipt scanning:** in-house OCR, with no third-party APIs
- 📍 **Location intelligence:** in-house reverse geocoding (country → division → district → thana), nearby shops, regional price comparison
- 🏪 **Shops:** shop owners and customers, orders, VAT and discounts, and due/advance/balance tracking
- 🗣️ **Voice and quick entry**
- 🌐 **Offline-first** with automatic sync
- 🇧🇩 **English + বাংলা** · light and dark themes

## 🏗️ Architecture
```mermaid
flowchart LR
    APP["React Native · Expo<br/>TypeScript · RTK Query"] -- "REST + WebSocket" --> NG["Nginx · SSL/TLS"]
    NG --> API["Spring Boot · Java 21<br/>JPA · WebSocket · JWT"]
    API --> DB[("MySQL")]
    API --> R[("Redis")]
    FB["Firebase Auth"] -.-> APP
    subgraph OCI["Oracle Cloud · Docker"]
      NG
      API
      DB
      R
    end
```

| Layer | Technology |
|---|---|
| Mobile | React Native, Expo, TypeScript, Redux Toolkit / RTK Query |
| Backend | Java 21, Spring Boot, Spring Data JPA, WebSocket, JWT |
| Data | MySQL, Redis cache |
| Auth | Firebase Authentication (Google + email) |
| Infra | Docker, Nginx, SSL/TLS on Oracle Cloud Infrastructure |
| Release | EAS Build → Google Play |

## 🛠️ Engineering highlights
- Designed, built, deployed and published **solo**: 276 commits across the mobile and backend monorepo
- Real-time sync, plus an offline-first data layer
- Custom OCR and geolocation pipelines instead of paid third-party APIs
- Started as my BUET PGD final project and grew into a production app

## 📬 Contact
Feedback, partnerships or similar product builds: **md.alhussain365@gmail.com** · [alhusso.com](https://alhusso.com)
