# 🛣️ Namma Rasthe Health – Rural Road Maintenance Tracking Application

<div align="center">

![Namma Rasthe Health](https://img.shields.io/badge/Namma%20Rasthe%20Health-Android%20App-brightgreen?style=flat-square&logo=android)
![Kotlin](https://img.shields.io/badge/Language-Kotlin-7F52FF?style=flat-square&logo=kotlin)
![MVVM](https://img.shields.io/badge/Architecture-MVVM-blue?style=flat-square)
![Room Database](https://img.shields.io/badge/Database-Room-4CAF50?style=flat-square&logo=sqlite)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-success?style=flat-square)

**A digital solution to report, monitor, and manage rural road damage efficiently**

[Features](#-key-features) • [Installation](#-installation-steps) • [Architecture](#-system-architecture) • [Contributors](#-contributors)

</div>

---

## 📋 Table of Contents

- [Project Description](#project-description)
- [Problem Statement](#problem-statement)
- [Key Features](#-key-features)
- [Technologies Used](#-technologies-used)
- [System Architecture](#-system-architecture)
- [Project Structure](#-project-structure)
- [Modules Overview](#-modules-overview)
- [Installation Steps](#-installation-steps)
- [How to Run the Project](#-how-to-run-the-project)
- [Screenshots](#-screenshots)
- [Database Details](#-database-details)
- [GPS and Google Maps Integration](#-gps-and-google-maps-integration)
- [Road Health Score Logic](#-road-health-score-logic)
- [Future Enhancements](#-future-enhancements)
- [Project Outcomes](#-project-outcomes)
- [Contributors](#-contributors)
- [License](#-license)

---

## 📱 Project Description

**Namma Rasthe Health** is an innovative Android-based application designed to digitize the process of reporting and managing rural road maintenance. It empowers citizens and Gram Panchayat (village council) officers to:

- Report road damage with precise GPS coordinates
- Monitor road health status across regions
- Track repair progress in real-time
- Access contractor information and updates
- Visualize road networks on interactive maps
- Maintain offline data synchronization

The application aims to bridge the gap between citizens and local authorities in ensuring better road infrastructure maintenance in rural areas.

---

## 🎯 Problem Statement

### Current Challenges:
- **Limited Transparency**: Citizens have no centralized platform to report road issues
- **Poor Coordination**: Gram Panchayat officers lack real-time visibility of road conditions
- **Inefficient Tracking**: Manual record-keeping delays road maintenance processes
- **Data Loss**: No systematic way to store and retrieve historical road data
- **Geographic Challenges**: Difficulty in locating and prioritizing damaged road sections

### Solution:
Namma Rasthe Health provides a **digital, location-aware, and user-friendly solution** that democratizes road maintenance reporting and management.

---

## ✨ Key Features

### 🗺️ **Road Directory**
- Comprehensive list of all roads in the region
- Road classification by type (National Highway, State Road, Village Road, etc.)
- Status filtering and search functionality
- Quick access to road details and history

### 📍 **GPS-Tagged Damage Reporting**
- One-tap damage reporting with automatic GPS coordinates
- Photo attachment support for documentation
- Damage categorization (Pothole, Crack, Water Logging, etc.)
- Real-time location tracking with accuracy details

### 🗺️ **Google Maps Integration**
- Interactive map visualization of all roads
- Real-time marker display for damage reports
- Color-coded status indicators on the map
- Route navigation to specific road sections
- Offline map caching support

### 📊 **Road Health Status Dashboard**
- Visual health indicators: 🟢 **Green** (Good), 🟠 **Orange** (Fair), 🔴 **Red** (Poor)
- Percentage-based health score calculation
- Historical trend analysis
- Regional health comparisons

### 📈 **Taluka Dashboard**
- Overview of all roads in a taluka (administrative division)
- Aggregate statistics and metrics
- Reports sorted by priority and urgency
- Export capabilities for administrative use

### 👷 **Contractor Information**
- Dedicated contractor management module
- Work allocation and progress tracking
- Contact information and availability
- Performance metrics and work history

### 💾 **Room Database Offline Storage**
- Local data persistence using Room ORM
- Automatic sync when connectivity is available
- Encrypted sensitive information
- Backup and restore functionality

### 🎨 **Material Design UI**
- Modern, intuitive user interface
- Consistent design patterns across app
- Accessibility features for inclusive usage
- Dark mode support

### 📑 **RecyclerView-Based Listings**
- Efficient data display with smooth scrolling
- Pagination support for large datasets
- Customizable list filters and sorting
- Pull-to-refresh functionality

---


## 📦 Installation Steps

### Prerequisites

- **Android Studio**: 2022.1.1 or later ([Download](https://developer.android.com/studio))
- **JDK**: Java 11 or later
- **Gradle**: 7.0 or later (bundled with Android Studio)
- **Minimum SDK**: Android 5.0 (API 21)
- **Target SDK**: Android 13 (API 33) or later
- **Physical Device/Emulator**: With GPS and internet capabilities

### Step 1: Clone the Repository

```bash
# Using HTTPS
git clone https://github.com/llsandeep01ll/Namma-Rasthe-Health.git

# Using SSH
git clone git@github.com:llsandeep01ll/Namma-Rasthe-Health.git

# Navigate to project directory
cd Namma-Rasthe-Health
```

### Step 2: Configure Google Maps API Key

1. **Generate API Key**:
   - Visit [Google Cloud Console](https://console.cloud.google.com/)
   - Create a new project
   - Enable Google Maps Android API
   - Create an API key

2. **Add API Key to Project**:
   - Open `local.properties` file:
   ```properties
   # local.properties
   MAPS_API_KEY=YOUR_API_KEY_HERE
   ```
   - Or add to `AndroidManifest.xml`:
   ```xml
   <meta-data
       android:name="com.google.android.geo.API_KEY"
       android:value="YOUR_API_KEY_HERE" />
   ```

### Step 3: Open in Android Studio

1. **Open Android Studio**
2. **Select** `File → Open...`
3. **Navigate** to the cloned repository folder
4. **Click** `Open`
5. **Wait** for Gradle indexing to complete

### Step 4: Gradle Sync

```bash
# Android Studio will automatically prompt for sync
# Or manually:
# File → Sync Now
# Or use terminal:
./gradlew sync
```

### Step 5: Resolve Dependencies

```bash
# Clean and rebuild
./gradlew clean build

# If there are issues with dependencies:
./gradlew build --refresh-dependencies
```

### Step 6: Configure Emulator or Physical Device

**Using Android Emulator**:
1. **Open AVD Manager** in Android Studio
2. **Create Virtual Device** (if not already created)
3. **Select Device**: Pixel 4 or higher
4. **Select API Level**: 21 or higher
5. **Enable GPS**: In AVD settings

**Using Physical Device**:
1. **Enable Developer Mode**: Settings → About Phone → Tap Build Number 7 times
2. **Enable USB Debugging**: Settings → Developer Options → USB Debugging
3. **Connect to Computer** via USB
4. **Accept USB Debugging** prompt on device

---

## ▶️ How to Run the Project

### Method 1: Using Android Studio

1. **Select Run Configuration**:
   - At the top toolbar, select the app configuration dropdown
   - Choose your emulator or connected device

2. **Click Run Button**:
   - Click the green ▶️ **Run** button
   - Or press `Shift + F10`

3. **Wait for Build and Installation**:
   - Android Studio will compile the project
   - Install the APK on the selected device
   - App will launch automatically

### Method 2: Using Command Line

```bash
# Build debug APK
./gradlew assembleDebug

# Install on connected device
./gradlew installDebug

# Run directly (build + install + launch)
./gradlew runDebug
```

### Method 3: Build Release APK

```bash
# Generate release APK
./gradlew assembleRelease

# Find APK at:
# app/build/outputs/apk/release/app-release.apk
```

### First Run Setup

1. **Grant Permissions**:
   - Location (GPS)
   - Camera
   - Storage
   - Internet

2. **Map Initialization**:
   - Allow map to load (first time may take a few seconds)
   - Grant location permissions when prompted

3. **Database Initialization**:
   - App automatically creates Room database
   - Initial data loads from remote API (if available)

---

## 📸 Screenshots

### Main Dashboard
```


```

### Road Directory


*Shows comprehensive list of roads with their health status and quick actions*

### Damage Reporting


*GPS-tagged damage report form with photo attachment and categorization*

### Google Maps


*Interactive map showing road network with colored health status markers*


### Contractor Information


*Contractor details, work allocation, and performance tracking*

---


### Core Development Team

| Name | Role | Contact |
|------|------|---------|
| **Sandeep N V** | Project Lead & Developer | [@llsandeep01ll](https://github.com/llsandeep01ll) |



---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](./LICENSE) file for details.

---



### Contact Information

- **Project Lead**: Sandeep N V
- **Email**: ll.sandeep01.ll@gmail.com
- **GitHub**: [@llsandeep01ll](https://github.com/llsandeep01ll)

---


---


