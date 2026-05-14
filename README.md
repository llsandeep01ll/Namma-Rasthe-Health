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

## 🛠️ Technologies Used

| Component | Technology | Version |
|-----------|-----------|---------|
| **Language** | Kotlin | 1.8+ |
| **Platform** | Android | API 21+ |
| **Architecture** | MVVM | - |
| **UI Framework** | XML Layouts | AndroidX |
| **Database** | Room ORM | 2.5+ |
| **Mapping** | Google Maps SDK | 18.0+ |
| **Location Services** | Google Play Services | 21.0+ |
| **Network** | Retrofit 2 | 2.9+ |
| **Async Processing** | Coroutines | 1.6+ |
| **Image Loading** | Glide | 4.14+ |
| **Dependency Injection** | Hilt | 2.44+ |
| **Testing** | JUnit 4, Espresso | - |
| **Build Tool** | Gradle | 7.0+ |

---

## 🏛️ System Architecture

### MVVM Architecture Pattern

```
┌─────────────────────────────────────────────────┐
│                   UI Layer                       │
│         (Activities, Fragments, Adapters)        │
└────────────────────┬────────────────────────────┘
                     │
���────────────────────▼────────────────────────────┐
│              ViewModel Layer                     │
│         (Business Logic & State Management)      │
└────────────────────┬────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────┐
│            Repository Layer                      │
│    (Data Abstraction & Source Management)        │
└────────────────────┬────────────────────────────┘
                     │
        ┌────────────┴────────────┐
        │                         │
┌───────▼────────┐      ┌────────▼────────┐
│  Local Data    │      │  Remote Data    │
│ (Room DB)      │      │  (API Server)   │
└────────────────┘      └─────────────────┘
```

### Data Flow:
1. **UI Layer** - User interactions trigger ViewModel functions
2. **ViewModel** - Manages UI state and business logic
3. **Repository** - Abstracts data sources (local & remote)
4. **Data Sources** - Room Database and REST API
5. **Response** - Data flows back through LiveData/StateFlow

---

## 📁 Project Structure

```
Namma-Rasthe-Health/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── kotlin/com/example/nammarasthe/
│   │   │   │   ├── ui/
│   │   │   │   │   ├── activities/
│   │   │   │   │   │   ├── MainActivity.kt
│   │   │   │   │   │   ├── RoadDetailActivity.kt
│   │   │   │   │   │   ├── DamageReportActivity.kt
│   │   │   │   │   │   └── DashboardActivity.kt
│   │   │   │   │   ├── fragments/
│   │   │   │   │   │   ├── RoadDirectoryFragment.kt
│   │   │   │   │   │   ├── MapFragment.kt
│   │   │   │   │   │   ├── TalukaDashboardFragment.kt
│   │   │   │   │   │   ├── ContractorFragment.kt
│   │   │   │   │   │   └── ProfileFragment.kt
│   │   │   │   │   ├── adapters/
│   │   │   │   │   │   ├── RoadListAdapter.kt
│   │   │   │   │   │   ├── DamageReportAdapter.kt
│   │   │   │   │   │   └── ContractorAdapter.kt
│   │   │   │   │   └── viewholders/
│   │   │   │   │       ├── RoadViewHolder.kt
│   │   │   │   │       └── DamageViewHolder.kt
│   │   │   │   │
│   │   │   │   ├── viewmodel/
│   │   │   │   │   ├── RoadViewModel.kt
│   │   │   │   │   ├── DamageReportViewModel.kt
│   │   │   │   │   ├── DashboardViewModel.kt
│   │   │   │   │   └── SharedViewModel.kt
│   │   │   │   │
│   │   │   │   ├── data/
│   │   │   │   │   ├── local/
│   │   │   │   │   │   ├── database/
│   │   │   │   │   │   │   ├── AppDatabase.kt
│   │   │   │   │   │   │   └── Migrations.kt
│   │   │   │   │   │   ├── dao/
│   │   │   │   │   │   │   ├── RoadDao.kt
│   │   │   │   │   │   │   ├── DamageReportDao.kt
│   │   │   │   │   │   │   └── ContractorDao.kt
│   │   │   │   │   │   └── preferences/
│   │   │   │   │   │       └── SharedPreferencesManager.kt
│   │   │   │   │   ├── remote/
│   │   │   │   │   │   ├── api/
│   │   │   │   │   │   │   ├── ApiService.kt
│   │   │   │   │   │   │   └── ApiClient.kt
│   │   │   │   │   │   └── response/
│   │   │   │   │   │       ├── RoadResponse.kt
│   │   │   │   │   │       └── DamageResponse.kt
│   │   │   │   │   └── repository/
│   │   │   │   │       ├── RoadRepository.kt
│   │   │   │   │       ├── DamageReportRepository.kt
│   │   │   │   │       └── ContractorRepository.kt
│   │   │   │   │
│   │   │   │   ├── model/
│   │   │   │   │   ├── Road.kt
│   │   │   │   │   ├── DamageReport.kt
│   │   │   │   │   ├── Contractor.kt
│   │   │   │   │   └── HealthScore.kt
│   │   │   │   │
│   │   │   │   ├── utils/
│   │   │   │   │   ├── Constants.kt
│   │   │   │   │   ├── LocationUtils.kt
│   │   │   │   │   ├── HealthScoreCalculator.kt
│   │   │   │   │   ├── DateUtils.kt
│   │   │   │   │   └── PermissionManager.kt
│   │   │   │   │
│   │   │   │   ├── di/
│   │   │   │   │   ├── DatabaseModule.kt
│   │   │   │   │   ├── NetworkModule.kt
│   │   │   │   │   └── RepositoryModule.kt
│   │   │   │   │
│   │   │   │   └── MyApplication.kt
│   │   │   │
│   │   │   └── res/
│   │   │       ├── layout/
│   │   │       │   ├── activity_main.xml
│   │   │       │   ├── activity_road_detail.xml
│   │   │       │   ├── activity_damage_report.xml
│   │   │       │   ├── fragment_road_directory.xml
│   │   │       │   ├── fragment_map.xml
│   │   │       │   └── item_road_list.xml
│   │   │       ├── drawable/
│   │   │       │   ├── ic_road.xml
│   │   │       │   ├── ic_damage.xml
│   │   │       │   ├── ic_map.xml
│   │   │       │   └── ic_dashboard.xml
│   │   │       ├── values/
│   │   │       │   ├── strings.xml
│   │   │       │   ├── colors.xml
│   │   │       │   ├── dimens.xml
│   │   │       │   └── themes.xml
│   │   │       └── menu/
│   │   │           └── bottom_navigation.xml
│   │   │
│   │   ├── test/
│   │   │   ├── java/com/example/nammarasthe/
│   │   │   │   ├── viewmodel/
│   │   │   │   ├── repository/
│   │   │   │   └── utils/
│   │   │   └── resources/
│   │   │
│   │   └── androidTest/
│   │       └── java/com/example/nammarasthe/
│   │           ├── ui/
│   │           └── integration/
│   │
│   └── build.gradle.kts
│
├── gradle/
│   └── wrapper/
│
├── settings.gradle.kts
├── build.gradle.kts
├── proguard-rules.pro
├── README.md
├── CONTRIBUTING.md
├── LICENSE
└── .gitignore

```

---

## 🧩 Modules Overview

### 1. **🗺️ Road Directory Module**
- **Responsibility**: Display and manage all roads in the system
- **Key Components**: 
  - `RoadListAdapter` - RecyclerView adapter for road listings
  - `RoadViewModel` - Handles road data and business logic
  - `RoadRepository` - Data access layer for roads
- **Features**:
  - Search and filter roads
  - Sort by name, status, health score
  - Quick view of road details

### 2. **📍 Damage Reporting Module**
- **Responsibility**: Enable users to report road damage with GPS coordinates
- **Key Components**:
  - `DamageReportActivity` - UI for damage reporting
  - `LocationUtils` - GPS location services
  - `DamageReportViewModel` - Business logic
  - `DamageReportDao` - Database operations
- **Features**:
  - Automatic GPS tagging
  - Photo attachment
  - Damage categorization
  - Real-time location validation

### 3. **🗺️ Google Maps Module**
- **Responsibility**: Visualize roads and damage reports on interactive maps
- **Key Components**:
  - `MapFragment` - Google Maps UI
  - `MapUtils` - Map operations and styling
- **Features**:
  - Road network visualization
  - Damage marker display
  - Color-coded health status
  - Route navigation
  - Offline map caching

### 4. **📊 Dashboard Module**
- **Responsibility**: Provide analytics and statistics
- **Key Components**:
  - `DashboardActivity` - Main dashboard UI
  - `TalukaDashboardFragment` - Taluka-level statistics
  - `DashboardViewModel` - Data aggregation
- **Features**:
  - Health score overview
  - Report statistics
  - Trend analysis
  - Export reports

### 5. **👷 Contractor Module**
- **Responsibility**: Manage contractor information and work allocation
- **Key Components**:
  - `ContractorFragment` - UI for contractor listings
  - `ContractorAdapter` - RecyclerView adapter
  - `ContractorRepository` - Data management
- **Features**:
  - Contractor details
  - Work assignment
  - Progress tracking
  - Performance metrics

### 6. **💾 Local Database Module**
- **Responsibility**: Manage offline data persistence
- **Key Components**:
  - `AppDatabase` - Room database configuration
  - DAOs for each entity
  - Migration strategies
- **Features**:
  - Offline data storage
  - Automatic sync
  - Data encryption
  - Backup restoration

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
┌─────────────────────────────────┐
│  Namma Rasthe Health     ⓘ  ☰   │
├─────────────────────────────────┤
│                                 │
│  📊 Health Overview             │
│  ├── 🟢 Good: 45%               │
│  ├── 🟠 Fair: 30%               │
│  └── 🔴 Poor: 25%               │
│                                 │
│  Recent Reports: 12             │
│  Pending Actions: 3             │
│                                 │
│  [View Dashboard]  [Report Damage]
│                                 │
├─────────────────────────────────┤
│  🏠  🗺️  📍  📊  👤             │
└─────────────────────────────────┘
```

### Road Directory
![Screenshot Placeholder - Road Directory](https://via.placeholder.com/540x960?text=Road+Directory+Screen)

*Shows comprehensive list of roads with their health status and quick actions*

### Damage Reporting
![Screenshot Placeholder - Damage Report](https://via.placeholder.com/540x960?text=Damage+Report+Screen)

*GPS-tagged damage report form with photo attachment and categorization*

### Google Maps
![Screenshot Placeholder - Google Maps](https://via.placeholder.com/540x960?text=Google+Maps+View)

*Interactive map showing road network with colored health status markers*

### Taluka Dashboard
![Screenshot Placeholder - Dashboard](https://via.placeholder.com/540x960?text=Taluka+Dashboard)

*Administrative overview with statistics, charts, and export options*

### Contractor Information
![Screenshot Placeholder - Contractors](https://via.placeholder.com/540x960?text=Contractor+List)

*Contractor details, work allocation, and performance tracking*

---

## 🗄️ Database Details

### Room Database Architecture

**Database Name**: `namma_rasthe_health_db`

**Version**: 1

**Entities**:

#### 1. **Road Entity**
```kotlin
@Entity(tableName = "roads")
data class Road(
    @PrimaryKey(autoGenerate = true)
    val id: Int = 0,
    
    @ColumnInfo(name = "road_name")
    val roadName: String,
    
    @ColumnInfo(name = "road_type")
    val roadType: String, // "National Highway", "State Road", "Village Road"
    
    @ColumnInfo(name = "length_km")
    val lengthKm: Double,
    
    @ColumnInfo(name = "taluka")
    val taluka: String,
    
    @ColumnInfo(name = "health_score")
    val healthScore: Float, // 0-100
    
    @ColumnInfo(name = "status")
    val status: String, // "GREEN", "ORANGE", "RED"
    
    @ColumnInfo(name = "last_updated")
    val lastUpdated: Long,
    
    @ColumnInfo(name = "latitude")
    val latitude: Double,
    
    @ColumnInfo(name = "longitude")
    val longitude: Double
)
```

#### 2. **DamageReport Entity**
```kotlin
@Entity(
    tableName = "damage_reports",
    foreignKeys = [ForeignKey(
        entity = Road::class,
        parentColumns = ["id"],
        childColumns = ["road_id"],
        onDelete = ForeignKey.CASCADE
    )]
)
data class DamageReport(
    @PrimaryKey(autoGenerate = true)
    val id: Int = 0,
    
    @ColumnInfo(name = "road_id")
    val roadId: Int,
    
    @ColumnInfo(name = "damage_type")
    val damageType: String, // "Pothole", "Crack", "Water Logging"
    
    @ColumnInfo(name = "severity")
    val severity: String, // "Low", "Medium", "High"
    
    @ColumnInfo(name = "latitude")
    val latitude: Double,
    
    @ColumnInfo(name = "longitude")
    val longitude: Double,
    
    @ColumnInfo(name = "photo_path")
    val photoPath: String?,
    
    @ColumnInfo(name = "description")
    val description: String,
    
    @ColumnInfo(name = "reported_by")
    val reportedBy: String,
    
    @ColumnInfo(name = "reported_date")
    val reportedDate: Long,
    
    @ColumnInfo(name = "status")
    val status: String, // "PENDING", "IN_PROGRESS", "RESOLVED"
    
    @ColumnInfo(name = "is_synced")
    val isSynced: Boolean = false
)
```

#### 3. **Contractor Entity**
```kotlin
@Entity(tableName = "contractors")
data class Contractor(
    @PrimaryKey(autoGenerate = true)
    val id: Int = 0,
    
    @ColumnInfo(name = "name")
    val name: String,
    
    @ColumnInfo(name = "phone")
    val phone: String,
    
    @ColumnInfo(name = "email")
    val email: String,
    
    @ColumnInfo(name = "taluka")
    val taluka: String,
    
    @ColumnInfo(name = "total_assignments")
    val totalAssignments: Int,
    
    @ColumnInfo(name = "completed_work")
    val completedWork: Int,
    
    @ColumnInfo(name = "rating")
    val rating: Float, // 0-5
    
    @ColumnInfo(name = "is_active")
    val isActive: Boolean
)
```

### DAO (Data Access Object) Methods

```kotlin
@Dao
interface RoadDao {
    @Insert
    suspend fun insertRoad(road: Road)
    
    @Query("SELECT * FROM roads WHERE taluka = :taluka")
    fun getRoadsByTaluka(taluka: String): Flow<List<Road>>
    
    @Query("SELECT * FROM roads WHERE id = :roadId")
    fun getRoadById(roadId: Int): Flow<Road>
    
    @Update
    suspend fun updateRoad(road: Road)
    
    @Delete
    suspend fun deleteRoad(road: Road)
}

@Dao
interface DamageReportDao {
    @Insert
    suspend fun insertReport(report: DamageReport)
    
    @Query("SELECT * FROM damage_reports WHERE road_id = :roadId")
    fun getReportsByRoad(roadId: Int): Flow<List<DamageReport>>
    
    @Query("SELECT * FROM damage_reports WHERE is_synced = 0")
    suspend fun getUnsyncedReports(): List<DamageReport>
}
```

### Database Migration Strategy

```kotlin
val MIGRATION_1_2 = object : Migration(1, 2) {
    override fun migrate(database: SupportSQLiteDatabase) {
        // Example migration script
        database.execSQL("""
            ALTER TABLE roads ADD COLUMN verified_date INTEGER
        """)
    }
}

@Database(
    entities = [Road::class, DamageReport::class, Contractor::class],
    version = 1,
    exportSchema = false
)
abstract class AppDatabase : RoomDatabase() {
    abstract fun roadDao(): RoadDao
    abstract fun damageReportDao(): DamageReportDao
    abstract fun contractorDao(): ContractorDao
}
```

---

## 📍 GPS and Google Maps Integration

### GPS Location Services

#### Requesting Location Permissions

```kotlin
// AndroidManifest.xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.INTERNET" />
```

#### LocationUtils Implementation

```kotlin
class LocationUtils(private val context: Context) {
    private lateinit var fusedLocationClient: FusedLocationProviderClient
    
    fun getLastKnownLocation(callback: (Double, Double) -> Unit) {
        fusedLocationClient = LocationServices.getFusedLocationProviderClient(context)
        
        if (ActivityCompat.checkSelfPermission(
            context,
            Manifest.permission.ACCESS_FINE_LOCATION
        ) != PackageManager.PERMISSION_GRANTED
        ) {
            return
        }
        
        fusedLocationClient.lastLocation.addOnSuccessListener { location ->
            if (location != null) {
                callback(location.latitude, location.longitude)
            }
        }
    }
    
    fun calculateDistance(lat1: Double, lon1: Double, lat2: Double, lon2: Double): Float {
        val results = FloatArray(1)
        Location.distanceBetween(lat1, lon1, lat2, lon2, results)
        return results[0]
    }
}
```

### Google Maps Implementation

#### MapFragment Setup

```kotlin
class MapFragment : Fragment(), OnMapReadyCallback {
    private lateinit var googleMap: GoogleMap
    
    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        val mapFragment = childFragmentManager.findFragmentById(R.id.map) 
            as SupportMapFragment
        mapFragment.getMapAsync(this)
    }
    
    override fun onMapReady(map: GoogleMap) {
        googleMap = map
        
        // Set map style
        googleMap.setMapStyle(
            MapStyleOptions.loadRawResourceStyle(
                requireContext(),
                R.raw.map_style
            )
        )
        
        // Configure initial position
        val initialLocation = LatLng(15.3173, 75.7139) // Example: Belgaum
        googleMap.moveCamera(CameraUpdateFactory.newLatLngZoom(initialLocation, 12f))
        
        // Load and display roads
        loadRoadsOnMap()
        
        // Add damage report markers
        loadDamageReportsOnMap()
    }
    
    private fun loadRoadsOnMap() {
        // Fetch roads from ViewModel
        viewModel.roads.observe(viewLifecycleOwner) { roads ->
            roads.forEach { road ->
                val marker = googleMap.addMarker(
                    MarkerOptions()
                        .position(LatLng(road.latitude, road.longitude))
                        .title(road.roadName)
                        .snippet("Status: ${road.status}")
                        .icon(getMarkerIcon(road.status))
                )
            }
        }
    }
    
    private fun getMarkerIcon(status: String): BitmapDescriptor {
        val color = when (status) {
            "GREEN" -> BitmapDescriptorFactory.HUE_GREEN
            "ORANGE" -> BitmapDescriptorFactory.HUE_ORANGE
            "RED" -> BitmapDescriptorFactory.HUE_RED
            else -> BitmapDescriptorFactory.HUE_BLUE
        }
        return BitmapDescriptorFactory.defaultMarker(color)
    }
}
```

#### Map Styling with JSON

```json
// res/raw/map_style.json
[
  {
    "featureType": "road",
    "elementType": "geometry",
    "stylers": [
      { "color": "#f5f1d7" },
      { "lightness": 20 }
    ]
  },
  {
    "featureType": "road",
    "elementType": "labels.text.fill",
    "stylers": [
      { "color": "#805c56" }
    ]
  }
]
```

### Polyline Drawing for Roads

```kotlin
// Draw roads as polylines
fun drawRoadPolyline(road: Road, coordinates: List<LatLng>) {
    val polyline = googleMap.addPolyline(
        PolylineOptions()
            .addAll(coordinates)
            .color(getStatusColor(road.status))
            .width(8f)
            .geodesic(true)
            .clickable(true)
    )
    
    polyline.tag = road.id
}

fun getStatusColor(status: String): Int {
    return when (status) {
        "GREEN" -> Color.parseColor("#4CAF50")
        "ORANGE" -> Color.parseColor("#FF9800")
        "RED" -> Color.parseColor("#F44336")
        else -> Color.parseColor("#2196F3")
    }
}
```

---

## 📊 Road Health Score Logic

### Health Score Calculation Algorithm

The road health score is calculated based on multiple factors:

```
Health Score = 100 - (Damage Weight × 100)

Where:
Damage Weight = (Σ(Damage Count × Severity Factor × Recency Factor)) / Total Possible Score
```

### Implementation

```kotlin
class HealthScoreCalculator {
    
    fun calculateRoadHealthScore(
        road: Road,
        damageReports: List<DamageReport>
    ): Float {
        if (damageReports.isEmpty()) {
            return 100f
        }
        
        val severityWeights = mapOf(
            "Low" to 0.1f,
            "Medium" to 0.5f,
            "High" to 1.0f
        )
        
        val damageTypeWeights = mapOf(
            "Pothole" to 1.0f,
            "Crack" to 0.7f,
            "Water Logging" to 0.5f
        )
        
        var totalDamageScore = 0f
        val currentTime = System.currentTimeMillis()
        
        damageReports.forEach { report ->
            val severity = severityWeights[report.severity] ?: 0.5f
            val damageType = damageTypeWeights[report.damageType] ?: 0.5f
            
            // Recency factor: older reports have less impact
            val ageInDays = (currentTime - report.reportedDate) / (1000 * 60 * 60 * 24)
            val recencyFactor = 1f / (1f + (ageInDays / 30f))
            
            totalDamageScore += severity * damageType * recencyFactor
        }
        
        val healthScore = 100f - (totalDamageScore * 10f)
        return healthScore.coerceIn(0f, 100f)
    }
    
    fun getHealthStatus(score: Float): String {
        return when {
            score >= 70 -> "GREEN"      // Good condition
            score >= 40 -> "ORANGE"     // Fair condition
            else -> "RED"               // Poor condition
        }
    }
    
    fun getHealthDescription(status: String): String {
        return when (status) {
            "GREEN" -> "Good - Regular maintenance only"
            "ORANGE" -> "Fair - Inspection and repairs needed"
            "RED" -> "Poor - Urgent repair required"
            else -> "Unknown"
        }
    }
}
```

### Health Score Categories

| Score Range | Status | Action |
|------------|--------|--------|
| **70-100** | 🟢 **GREEN** | Regular maintenance only |
| **40-69** | 🟠 **ORANGE** | Inspection & repairs needed |
| **0-39** | 🔴 **RED** | Urgent repair required |

### Visualization in Dashboard

```
Road Health Overview

🟢 Good (Score ≥ 70)
├── Highway-1: 85/100
├── State Road-2: 78/100
└── 23 more roads

🟠 Fair (Score 40-69)
├── Village Road-5: 55/100
├── Rural Lane-3: 48/100
└── 12 more roads

🔴 Poor (Score < 40)
├── Connector Road-1: 25/100
├── Old Road-4: 32/100
└── 5 more roads
```

---

## 🚀 Future Enhancements

### Phase 2 (Q3 2026)
- [ ] **Citizen Notifications**: Real-time alerts for nearby road repairs
- [ ] **Augmented Reality (AR)**: Virtual visualization of repairs
- [ ] **Machine Learning Integration**: Predictive damage detection using image analysis
- [ ] **Weather Integration**: Correlation between weather and road damage
- [ ] **Multi-language Support**: Hindi, Marathi, Kannada, Telugu translations

### Phase 3 (Q4 2026)
- [ ] **IoT Integration**: Smart sensors on roads for real-time monitoring
- [ ] **Blockchain Integration**: Transparent work completion verification
- [ ] **Advanced Analytics**: Predictive maintenance scheduling
- [ ] **Social Features**: Community-driven road safety initiatives
- [ ] **Mobile App Performance**: Optimization for low-bandwidth areas

### Phase 4 (2027)
- [ ] **Web Portal**: Administrative dashboard for government officials
- [ ] **API Marketplace**: Integration with third-party applications
- [ ] **Cross-platform Support**: Web and desktop applications
- [ ] **Advanced Reporting**: Custom report generation and export
- [ ] **Disaster Management**: Integration with disaster response systems

---

## 📈 Project Outcomes

### Impact Metrics

| Metric | Target | Current |
|--------|--------|---------|
| **Users** | 50,000+ | - |
| **Roads Tracked** | 5,000+ | - |
| **Average Response Time** | < 48 hours | - |
| **Repair Completion Rate** | > 90% | - |
| **User Satisfaction** | > 4.5/5 | - |

### Key Achievements

✅ **Transparent Governance**: Citizens can directly report and track issues

✅ **Improved Maintenance**: Data-driven prioritization of repairs

✅ **Cost Optimization**: Efficient resource allocation and reduction in wastage

✅ **Community Engagement**: Citizen participation in infrastructure development

✅ **Digital Records**: Permanent, searchable history of all road issues

### Beneficiaries

- **Citizens**: Easy reporting and tracking mechanisms
- **Gram Panchayat**: Better oversight and management capabilities
- **Contractors**: Clear work assignments and performance metrics
- **Government**: Data-driven policy making and resource planning

---

## 👥 Contributors

### Core Development Team

| Name | Role | Contact |
|------|------|---------|
| **Sandeep N V** | Project Lead & Developer | [@llsandeep01ll](https://github.com/llsandeep01ll) |
| TBD | UI/UX Designer | - |
| TBD | QA Engineer | - |
| TBD | Backend Developer | - |

### How to Contribute

We welcome contributions! Please follow these guidelines:

1. **Fork the Repository**
   ```bash
   git clone https://github.com/llsandeep01ll/Namma-Rasthe-Health.git
   ```

2. **Create Feature Branch**
   ```bash
   git checkout -b feature/YourFeatureName
   ```

3. **Commit Changes**
   ```bash
   git commit -m "Add: Brief description of changes"
   ```

4. **Push to Branch**
   ```bash
   git push origin feature/YourFeatureName
   ```

5. **Open Pull Request**
   - Provide clear description of changes
   - Include relevant issue numbers
   - Ensure all tests pass

### Code Style Guide

- **Kotlin Best Practices**: Follow [Kotlin Coding Conventions](https://kotlinlang.org/docs/coding-conventions.html)
- **Naming**: Use camelCase for variables/methods, PascalCase for classes
- **Comments**: Write meaningful comments for complex logic
- **Testing**: Include unit tests for all new features
- **Documentation**: Update README for significant changes

### Development Setup for Contributors

```bash
# Install Git
# Install Android Studio 2022.1.1+
# Clone repository
git clone https://github.com/llsandeep01ll/Namma-Rasthe-Health.git

# Open in Android Studio and wait for sync
# Configure Google Maps API key
# Run tests before committing
./gradlew test
```

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](./LICENSE) file for details.

### MIT License Summary

- ✅ **Permitted**: Commercial use, modification, distribution, private use
- ❌ **Not permitted**: Trademark use, liability claims
- ℹ️ **Conditions**: License and copyright notice required

---

## 📞 Support & Contact

### Getting Help

- **Issues & Bugs**: [GitHub Issues](https://github.com/llsandeep01ll/Namma-Rasthe-Health/issues)
- **Discussions**: [GitHub Discussions](https://github.com/llsandeep01ll/Namma-Rasthe-Health/discussions)
- **Documentation**: See [Wiki](https://github.com/llsandeep01ll/Namma-Rasthe-Health/wiki)

### Contact Information

- **Project Lead**: Sandeep N V
- **Email**: [Your Email]
- **GitHub**: [@llsandeep01ll](https://github.com/llsandeep01ll)

---

## 📚 Additional Resources

- [Android Developers Guide](https://developer.android.com/)
- [Kotlin Documentation](https://kotlinlang.org/docs/)
- [Google Maps API Documentation](https://developers.google.com/maps/documentation/android-sdk)
- [Room Database Guide](https://developer.android.com/training/data-storage/room)
- [MVVM Architecture](https://developer.android.com/jetpack/guide)

---

<div align="center">

### ⭐ If you find this project helpful, please consider giving it a star!

[⬆ Back to Top](#-namma-rasthe-health--rural-road-maintenance-tracking-application)

**Last Updated**: May 14, 2026

</div>
