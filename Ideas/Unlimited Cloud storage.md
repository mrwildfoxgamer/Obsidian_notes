- A front end that allows user to upload files into github privet repo
	- create privet repo
	- hold a json for each file and its download link


# V.0.0.1
# 📱 Git-Based Mobile Image Upload App — Final System Design Document

---

# 1. 📌 Overview

A **native mobile application** that allows users to upload **images only** to GitHub repositories using Git, with automated syncing, manual repo lifecycle control, and performance monitoring.

---

# 2. 🎯 Objectives

- Simple image upload workflow
    
- Avoid large file issues (no videos)
    
- Maintain performance via controlled repo size
    
- Keep system predictable (no automatic repo switching)
    

---

# 3. ⚙️ Core Features

## 3.1 Image Selection & Staging

- Supported formats:
    
    ```
    .jpg, .jpeg, .png, .webp
    ```
    
- Files are copied into repo folder:
    
    ```
    /images/YYYY/MM/
    ```
    

---

## 3.2 Auto Sync Engine

### Workflow:

```
git add .
git commit -m "Added new images"
git push
```

### Behavior:

- Triggered after adding images
    
- Batched (10–30 sec delay)
    
- Retry on failure
    
- Offline queue supported
    

---

## 3.3 Delete After Upload (Optional)

### Modes:

- **Safe Mode** → keep images locally
    
- **Clean Mode** → delete after successful push
    

---

## 3.4 Repo Size Monitoring 🚨

### Method:

```
git count-objects -vH
```

### Threshold:

- Warning at **2GB**
    

---

## 3.5 Repo Management (Manual Control Only)

### Key Rule:

❌ No auto repo switching

### When repo exceeds limit:

- App shows warning:
    
    > Repository size exceeded 2GB. Create a new repo for better performance.
    

---

## 3.6 New Repo Creation Flow 🆕

When user decides to create a new repo:

### Steps:

1. User selects **new local folder**
    
2. App initializes new repo:
    
    ```
    git init
    ```
    
3. App creates new GitHub repo via API
    
4. Connect remote:
    
    ```
    git remote add origin <repo_url>
    ```
    
5. Start fresh uploads
    

---

## 3.7 Automated Repo Naming Scheme 🧠

### Format:

```
image-backup-YYYY-MM-XX
```

### Examples:

```
image-backup-2026-03-01
image-backup-2026-03-02
```

### Logic:

- YYYY → year
    
- MM → month
    
- XX → sequence number
    

✔ Ensures:

- No naming conflicts
    
- Clean chronological order
    
- Easy repo identification
    

---

## 3.8 Multi-Repo Folder Structure

```
/uploads_2026_1
/uploads_2026_2
/uploads_2026_3
```

Each folder = separate Git repo

---

# 4. 📊 Dashboard Feature

## 4.1 Repository Info

- Repo name
    
- Total size
    
- Image count
    

---

## 4.2 Sync Status

- Last sync time
    
- Status:
    
    - ✅ Success
        
    - ⏳ In progress
        
    - ❌ Failed
        

---

## 4.3 Storage Usage

- Progress bar
    
- Alerts:
    
    - 1.5GB → warning
        
    - 2GB → critical
        

---

## 4.4 Upload Activity

- Recently uploaded images
    
- Timestamps
    

---

## 4.5 Performance Metrics

- Upload speed
    
- Pending queue size
    
- Sync frequency
    

---

## 4.6 Repo Lifecycle

- Active repo
    
- Total repos created
    
- Current folder in use
    

---

# 5. 🧠 System Architecture

## Components:

### 📱 Mobile App

- UI + Dashboard
    
- Image picker (restricted)
    
- Background sync service
    
- Git integration (JGit / libgit2)
    

---

### ⚙️ Git Engine

- add / commit / push
    
- repo size calculation
    

---

### 🔐 GitHub Integration

- OAuth login
    
- Repo creation API
    

---

### 🔄 Background Service

- Handles sync queue
    
- Periodic repo checks
    

---

# 6. 🔄 Workflow Summary

## Initial Setup:

1. Login with GitHub
    
2. Select/create repo
    
3. Choose local folder
    

---

## Upload Flow:

1. Select images
    
2. Copy to repo folder
    
3. Auto sync
    
4. Commit + push
    
5. Optional deletion
    

---

## Repo Limit Flow:

1. Repo size checked
    
2. If >2GB:
    
    - Show warning
        
    - User manually creates new repo (new folder)
        

---

# 9. 🧪 Edge Cases

- No internet → queue uploads
    
- Push failure → retry
    
- Duplicate filenames → rename
    
- Merge conflicts → auto pull + retry
    

---

# 10. 🚀 Final Summary

This app is a:

👉 **Controlled, Git-based image backup system**

Key strengths:

- Manual repo lifecycle (predictable)
    
- Automated uploads
    
- Clean naming system
    
- Performance-aware design
    
- Real-time dashboard monitoring
    

---

#  Development Roadmap

## Phase 0 — Foundation (1–2 days)

### Setup:

- Android Studio (latest)
    
- Kotlin + Jetpack Compose project
    
- Git repo for your app
    

### Add core dependencies:

- Compose
    
- ViewModel
    
- Hilt
    
- Navigation Compose
    
- Room
    
- WorkManager
    
- OkHttp
    
- JGit
    

---

## 🔐 Phase 1 — GitHub Authentication (2–3 days)

### Goal:

User logs in with their **own GitHub account**

### Implementation:

- Use **GitHub OAuth Device Flow**
    
- Get access token
    
- Store token (DataStore)
    

### Output:

- Logged-in state
    
- Token available for API + Git
    

---

## 📁 Phase 2 — Repo Setup System (3–4 days)

### Features:

- Select local folder
    
- Initialize repo:
    
    ```
    git init
    ```
    
- Create repo via GitHub API
    
- Connect remote:
    
    ```
    git remote add origin
    ```
    

### Add naming logic:

```
image-backup-YYYY-MM-XX
```

### Output:

- Fully working repo linked to GitHub
    

---

## 🖼️ Phase 3 — Image Selection System (2 days)

### Use:

- Android Photo Picker
    

### Constraints:

- Only allow:
    
    ```
    jpg, png, webp
    ```
    

### Logic:

- Copy images → repo folder
    

```
/images/YYYY/MM/
```

### Edge handling:

- Rename duplicates
    

---

## ⚙️ Phase 4 — Git Engine (Core Feature) (4–5 days)

### Using JGit:

Implement:

```
git add .
git commit -m "Added images"
git push
```

### Handle:

- First push (set upstream)
    
- Auth with token
    

### Output:

- Images pushed to GitHub
    

---

## 🔄 Phase 5 — Background Sync Engine (5–6 days)

### Use:

- WorkManager
    

### Features:

- Batch uploads (10–30 sec delay)
    
- Retry on failure
    
- Offline queue
    

### Flow:

1. Add images → enqueue job
    
2. Worker executes:
    
    - add → commit → push
        

---

## 🧠 Phase 6 — Local Database (Room) (3–4 days)

### Tables:

#### UploadQueue

- file_path
    
- status
    
- retry_count
    

#### RepoInfo

- repo_name
    
- local_path
    
- size
    
- created_at
    

#### SyncLog

- timestamp
    
- status
    
- message
    

---

## 📊 Phase 7 — Dashboard UI (4–5 days)

### Build screens:

#### 1. Repo Info

- Name
    
- Size
    
- Image count
    

#### 2. Sync Status

- Last sync
    
- Status
    

#### 3. Storage Bar

- Progress (1.5GB warning, 2GB critical)
    

#### 4. Activity Feed

- Recent uploads
    

#### 5. Performance

- Queue size
    
- Upload speed
    

---

## 🚨 Phase 8 — Repo Size Monitoring (2–3 days)

### Method:

```
git count-objects -vH
```

### Logic:

- > 1.5GB → warning
    
- > 2GB → block upload
    

### UI:

- Alert user
    
- Suggest new repo
    

---

## 🆕 Phase 9 — New Repo Flow (3 days)

### Flow:

1. User selects new folder
    
2. App:
    
    - `git init`
        
    - create GitHub repo
        
    - link remote
        

### Important:

❌ No auto switching  
✔ User decides manually

---

## 🧹 Phase 10 — Clean Mode (1–2 days)

### Logic:

```
IF push success AND Clean Mode:
    delete local file
```

### Add toggle in settings

---

## ⚠️ Phase 11 — Edge Case Handling (3–4 days)

Handle:

- No internet → queue
    
- Push failure → retry
    
- Merge conflict → pull + retry
    
- Token expired → re-login
    
- Duplicate filenames → rename
    

---

## 🎨 Phase 12 — UX Polish (3–4 days)

- Loading states
    
- Error messages
    
- Smooth transitions
    
- Minimal UI (fast usage)
    

---

## 🧪 Phase 13 — Testing (4–5 days)

### Test:

- Upload flow
    
- Offline → online sync
    
- Large repo warning
    
- Repo switching
    
- Failure recovery
    

---

## 📦 Phase 14 — Release (2 days)

- Build APK / AAB
    
- Internal testing
    
- Play Store (optional)
    

---

# 🧠 Final Architecture (Simple View)

```
UI (Compose)
   ↓
ViewModel
   ↓
Repository Layer
   ↓
--------------------------------
| Git Engine (JGit)            |
| GitHub API (OkHttp)          |
| Local DB (Room)              |
| Background Sync (WorkManager)|
--------------------------------
```

---


# 💡 Pro Tips 

- Start with **single repo only**
    
- Get **push working first** → everything else builds on that
    
- Don’t overcomplicate UI early
    
- Test with real GitHub repos early
    

---

# DAY 1

## First commit

You are an expert Android developer helping build a production-ready mobile app.

The project is called **GitPhos**. Below is the current setup state. Use this as context and guide the next implementation steps with clean architecture and best practices.

---

## Current Project State

### Project Setup

- Android project created using Kotlin
    
- Minimum SDK: 26
    
- Using Jetpack Compose
    
- Package structure initialized
    

---

### Gradle & Dependencies

- Kotlin version: 2.0.21
    
- KSP version: 2.0.21-1.0.25
    
- Android Gradle Plugin: 8.7.3
    

Dependencies already added:

- Jetpack Compose
    
- Hilt (dependency injection)
    
- Room (local database)
    
- WorkManager
    
- DataStore (preferences)
    
- OkHttp
    
- JGit (Android-compatible version)
    
- Coil (image loading)
    
- Coroutines
    

---

### Architecture

Project follows clean architecture with the following structure:

data / domain / ui / di / worker / util

---

### Permissions

The following permissions are already configured:

- INTERNET
    
- READ_MEDIA_IMAGES
    
- READ_EXTERNAL_STORAGE (maxSdk 28)
    
- WRITE_EXTERNAL_STORAGE (maxSdk 28)
    
- FOREGROUND_SERVICE
    
- FOREGROUND_SERVICE_DATA_SYNC
    

---

### Build Status

- Gradle sync is successful
    
- Build is successful
    
- All dependencies are resolved
    
- Only minor warnings exist (can be ignored)
    

---

## Instructions

- Be concise and structured
    
- Provide production-ready code
    
- Follow best practices for Android + Clean Architecture
    
- Avoid unnecessary verbosity
    
- One step at a time
Proceed step-by-step.

## What comes next

Once the project builds clean:

**Step 6** — Room schema (upload queue, sync history, repo metadata entities)  
**Step 7** — DataStore setup (auth token, active repo path, prefs)  
**Step 8** — GitHub OAuth flow (device flow or PAT input — device flow is simpler on mobile)  
**Step 9** — JGit wrapper class (init, add, commit, push, `count-objects`)  
**Step 10** — WorkManager SyncWorker skeleton  
**Step 11** — UI scaffolding (NavGraph + bottom nav)  
**Step 12** — Dashboard screen wired to real data

# DAY 2
You are an expert Android developer helping build a production-ready mobile app using Kotlin and Clean Architecture.

The project is called **GitPhos** — an app that uploads images to GitHub repositories using Git.

Use the following as the source of truth and guide further implementation.

---

# Current Project State

## Completed Features

### 1. Room Database (Complete)

- Entities:
    - UploadQueueEntity
    - SyncHistoryEntity
    - RepoMetadataEntity
- DAOs:
    - UploadQueueDao
    - SyncHistoryDao
    - RepoMetadataDao
- Database:
    - GitPhosDatabase with type converters
- DI:
    - Integrated via DatabaseModule (Hilt)

---

### 2. DataStore (Complete)

- Implemented:
    - Auth token storage
    - Active repository path
    - User preferences
- Structure:
    - PrefsDataStore
    - PrefsKeys
    - UserPrefs
- DI:
    - DataStoreModule

---

### 3. GitHub Authentication (Complete)

- Method:
    - Personal Access Token (PAT)
- API Layer:
    - GithubApi
    - DTO → Domain mapping (GithubUserDto → GithubUser)
- Repository:
    - AuthRepository
    - AuthRepositoryImpl
- Use Cases:
    - ValidateTokenUseCase
    - LogoutUseCase

---

# Architecture

Follows Clean Architecture:

- data/
    - Room, DataStore, API, (JGit — upcoming)
- domain/
    - Models, Repositories, UseCases
- ui/
    - Compose screens (pending)
- di/
    - Hilt modules:
        - NetworkModule
        - DatabaseModule
        - DataStoreModule
        - AuthModule
- worker/
    - (planned)
- util/

---

# Tech Stack

- Kotlin 2.0.21
- KSP
- Jetpack Compose
- Hilt
- Room
- WorkManager
- DataStore
- OkHttp
- JGit (Android-compatible)
- Coil
- Coroutines

---

# Permissions

Already configured:

- INTERNET
- READ_MEDIA_IMAGES
- READ_EXTERNAL_STORAGE (maxSdk 28)
- WRITE_EXTERNAL_STORAGE (maxSdk 28)
- FOREGROUND_SERVICE
- FOREGROUND_SERVICE_DATA_SYNC

---

# Build Status

- Build: Successful
- Gradle Sync: Clean
- Dependencies: Resolved

---

# Current Progress

- Data Layer: Complete
- Auth System: Complete
- Persistence: Complete
- Git Engine: Next
- Workers + UI: Pending

---

# Instructions

- Be concise and structured
- Provide production-ready Kotlin code
- Follow Clean Architecture best practices
- Avoid unnecessary explanations
- Proceed step-by-step (one step at a time)
- Prefer modular, testable, scalable design

---

# Next Step (Start Here)

## Step 9 — JGit Integration Layer

Implement a Git wrapper inside:

data/git/

---

## Requirements

Create a class or set of classes that handle:

- Initialize repository
- Clone repository (optional, future-ready)
- Add files
- Commit changes
- Push to remote (GitHub)
- Repository size check (count-objects)
- Branch handling (default: main)

---

## Expected Design

### Interface (Domain Layer)

GitRepository

---

### Implementation (Data Layer)

GitRepositoryImpl

---

## Functional Requirements

- Works with a local repository path
- Uses PAT authentication
- Handles errors safely
- Returns Result or sealed class states
- No UI logic

---

## Bonus (Optional)

- Progress callbacks (push)
- Logging support

---

# Constraints

- Must work on Android
- Avoid blocking main thread
- Use coroutines properly
- Keep implementation lightweight

---

# Next Steps After This

- Step 10 — WorkManager Sync Worker
- Step 11 — Upload Pipeline
- Step 12 — UI Layer


# DAY 5

current state App is now an android application with an authentication screen and if the token is valid then it moves to the dashboard(Dash board is yet to be build)

#### Steps remaning
12.2 Dashboard⏳ placeholder only
12.3 Image Picker⏳ not started
12.4 Repo Management⏳ not started
12.5 Sync⏳ not started



# GitPhos — AI Developer Handoff Prompt

## What We Are Building

**GitPhos** is a production-ready Android app that lets users upload images to a GitHub repository using Git (JGit). Users authenticate with a GitHub PAT, select images, and the app commits and pushes them to a configured GitHub repo via WorkManager background sync.

---

## Tech Stack

- **Language**: Kotlin
- **UI**: Jetpack Compose + Material3
- **Architecture**: Strict Clean Architecture (data / domain / ui / di / worker)
- **DI**: Hilt
- **Local DB**: Room
- **Preferences**: DataStore
- **Git**: JGit (`org.eclipse.jgit:org.eclipse.jgit:6.7.0`)
- **Background Sync**: WorkManager
- **Image Loading**: Coil
- **Networking**: Retrofit + Moshi + OkHttp
- **State Management**: MVI — ViewModel + State + Event + Effect pattern
- **Navigation**: Navigation Compose, single-activity
- **Package**: `com.example.gitphos`
- **Min SDK**: 26, Target SDK: 35, JVM: 17

---

## Project File Structure

```
app/src/main/java/com/example/gitphos/
├── data/
│   ├── git/GitRepositoryImpl.kt
│   ├── local/
│   │   ├── datastore/PrefsDataStore.kt, PrefsKeys.kt, UserPrefs.kt
│   │   ├── db/
│   │   │   ├── dao/RepoMetadataDao.kt, SyncHistoryDao.kt, UploadQueueDao.kt
│   │   │   ├── DatabaseModule.kt, GitPhosDatabase.kt, Converters.kt
│   │   └── entity/RepoMetadataEntity.kt, SyncHistoryEntity.kt, UploadQueueEntity.kt
│   ├── remote/GithubApi.kt, model/GithubUserDto.kt
│   └── repository/AuthRepositoryImpl.kt
├── di/
│   ├── AuthModule.kt, DataStoreModule.kt, GitModule.kt
│   ├── NetworkModule.kt, WorkerModule.kt
├── domain/
│   ├── model/GithubUser.kt, GitResult.kt, SyncResult.kt
│   ├── repository/AuthRepository.kt, GitRepository.kt
│   └── usecase/
│       ├── ValidateTokenUseCase.kt
│       ├── LogoutUseCase.kt
│       └── SyncUploadQueueUseCase.kt
├── ui/
│   ├── auth/
│   │   ├── AuthContract.kt   ← AuthState, AuthEvent, AuthEffect
│   │   ├── AuthViewModel.kt
│   │   └── AuthScreen.kt
│   ├── navigation/NavGraph.kt
│   └── theme/Color.kt, Theme.kt, Type.kt
├── worker/SyncWorker.kt, SyncScheduler.kt
├── GitPhosApp.kt
└── MainActivity.kt
```

---

## Domain Layer — Key Contracts

### AuthRepository

```kotlin
interface AuthRepository {
    suspend fun validateAndSaveToken(pat: String): Result<GithubUser>
    suspend fun logout()
    suspend fun getStoredToken(): String?
}
```

### GitRepository

```kotlin
interface GitRepository {
    suspend fun initRepository(localPath: String): GitResult<Unit>
    suspend fun cloneRepository(remoteUrl: String, localPath: String, token: String): GitResult<Unit>
    suspend fun addFiles(localPath: String, filePatterns: List<String>): GitResult<Unit>
    suspend fun commit(localPath: String, message: String, authorName: String, authorEmail: String): GitResult<Unit>
    suspend fun push(localPath: String, remoteUrl: String, token: String, branch: String = "main", onProgress: ((String) -> Unit)?): GitResult<Unit>
    suspend fun getRepoSize(localPath: String): GitResult<Long>
    suspend fun ensureBranch(localPath: String, branch: String = "main"): GitResult<Unit>
    suspend fun isValidRepo(localPath: String): Boolean
}
```

### Use Cases

|UseCase|Signature|Purpose|
|---|---|---|
|`ValidateTokenUseCase`|`invoke(pat: String): Result<GithubUser>`|Validates PAT + saves token via `validateAndSaveToken`|
|`LogoutUseCase`|`invoke()`|Clears stored token|
|`SyncUploadQueueUseCase`|`invoke(localRepoPath: String, remoteUrl: String): SyncResult`|Processes pending Room queue, commits + pushes each file|

### Models

```kotlin
// SyncResult
sealed class SyncResult {
    object Success : SyncResult()
    data class Failure(val message: String, val cause: Throwable? = null) : SyncResult()
    data class PartialSuccess(val uploaded: Int, val failed: Int) : SyncResult()
}

// GitResult
sealed class GitResult<out T> {
    data class Success<T>(val data: T) : GitResult<T>()
    data class Error(val message: String, val cause: Throwable? = null) : GitResult<Nothing>()
}
```

---

## Database — Room DAOs (already implemented)

- **`UploadQueueDao`**: `getPendingItems()`, `markInProgress(id)`, `markCompleted(id)`, `markFailed(id, reason)`
- **`SyncHistoryDao`**: `insert(entity)`, presumably `getAll()` / `getLatest()`
- **`RepoMetadataDao`**: stores repo URL + local path

---

## UI Layer — Current State

### ✅ Completed

- **Auth Screen** — full MVI implementation, working end-to-end
    - `AuthContract.kt` (AuthState, AuthEvent, AuthEffect)
    - `AuthViewModel.kt` — injects `ValidateTokenUseCase`
    - `AuthScreen.kt` — PAT input, show/hide toggle, loading, error states
- **Navigation** — `NavGraph.kt` with `Screen` sealed class, `authScreen()` extension
- **MainActivity** — `@AndroidEntryPoint`, NavHost wired, `authScreen` + `dashboardScreen` (placeholder) registered

### ⏳ Remaining Screens (build in this order)

#### Step 12.2 — Dashboard Screen (`ui/dashboard/`)

Show: selected repo, pending upload count, last sync status Actions: pick images, sync now, change repo, logout Needs: `UploadQueueDao` (pending count), `SyncHistoryDao` (last sync), `LogoutUseCase`, `RepoMetadataDao` (repo info)

#### Step 12.3 — Image Picker Screen (`ui/picker/`)

Select multiple images from device, preview grid, add to Room upload queue Needs: `UploadQueueDao.insert()`, Android photo picker / `ActivityResultContracts`

#### Step 12.4 — Repo Management Screen (`ui/repo/`)

Set GitHub repo remote URL + local path, save to DataStore/Room, basic URL validation Needs: `RepoMetadataDao`, `PrefsDataStore`

#### Step 12.5 — Sync Screen (`ui/sync/`)

Show upload progress per file, current file name, success/failure states Trigger WorkManager sync manually Needs: `SyncUploadQueueUseCase`, `SyncWorker`, `WorkManager`

---

## Navigation Routes

```kotlin
sealed class Screen(val route: String) {
    data object Auth : Screen("auth")
    data object Dashboard : Screen("dashboard")
    data object Picker : Screen("picker")
    data object Repo : Screen("repo")
    data object Sync : Screen("sync")
}
```

---

## MVI Pattern (enforce on every screen)

```
State     → immutable data class, single source of truth
Event     → sealed interface, user actions only
Effect    → sealed interface, one-time events (navigate, toast)

ViewModel → exposes StateFlow<State>, Flow<Effect> via Channel
Screen    → stateless composable, receives state + onEvent lambda
Route     → Hilt-aware composable, collects effects, owns side effects
```

---

## Code Rules (enforce strictly)

- No business logic in UI layer
- All coroutines via `viewModelScope`
- No blocking calls on main thread
- State hoisting on all composables
- `@Preview` for all screens (idle, loading, error states)
- Each screen in its own subpackage: `ui/dashboard/`, `ui/picker/`, etc.
- All files use package `com.example.gitphos.ui.<screen>`
- Navigation extensions go in `NavGraph.kt` as `NavGraphBuilder` extension functions
- After each screen: uncomment its route in `MainActivity.kt`

---

## Before You Start Each Screen — Ask For:

1. Contents of relevant DAOs if not shown above (e.g. `RepoMetadataDao`, `SyncHistoryDao`)
2. Contents of `PrefsDataStore` / `PrefsKeys` if DataStore reads/writes are needed
3. Contents of `SyncWorker` before building Sync screen
4. Any entity schema if inserting/reading from Room

Run this to get any file:

```bash
cat app/src/main/java/com/example/gitphos/<path>/<File>.kt
```

---

## Build Commands

```bash
./gradlew assembleDebug          # full build
./gradlew :app:kspDebugKotlin    # check Hilt/KSP only
./gradlew installDebug           # install on device
./gradlew :app:compileDebugKotlin --stacktrace 2>&1 | grep -i "e:" | head -30  # errors only
```

---

## Current Task

**Build Step 12.2 — Dashboard Screen** in `ui/dashboard/`.

Before generating any code, ask the developer to run:

```bash
cat app/src/main/java/com/example/gitphos/data/local/db/dao/UploadQueueDao.kt
cat app/src/main/java/com/example/gitphos/data/local/db/dao/SyncHistoryDao.kt
cat app/src/main/java/com/example/gitphos/data/local/db/dao/RepoMetadataDao.kt
cat app/src/main/java/com/example/gitphos/data/local/entity/RepoMetadataEntity.kt
cat app/src/main/java/com/example/gitphos/data/local/entity/SyncHistoryEntity.kt
cat app/src/main/java/com/example/gitphos/data/local/entity/UploadQueueEntity.kt
```

Then generate: DashboardViewModel, DashboardContract, DashboardScreen, and the `dashboardScreen()` nav entry in NavGraph.kt (replacing the current placeholder).



```
package com.example.gitphos.data.local.db.dao  
  
import androidx.room.*  
import com.example.gitphos.data.local.db.entity.RepoMetadataEntity  
import kotlinx.coroutines.flow.Flow  
  
@Dao  
interface RepoMetadataDao {  
  
    @Insert(onConflict = OnConflictStrategy.REPLACE)  
    suspend fun insert(repo: RepoMetadataEntity): Long  
  
    @Update  
    suspend fun update(repo: RepoMetadataEntity)  
  
    @Delete  
    suspend fun delete(repo: RepoMetadataEntity)  
  
    @Query("SELECT * FROM repo_metadata ORDER BY name ASC")  
    fun observeAll(): Flow<List<RepoMetadataEntity>>  
  
    @Query("SELECT * FROM repo_metadata WHERE id = :id")  
    suspend fun getById(id: Long): RepoMetadataEntity?  
  
    @Query("SELECT * FROM repo_metadata WHERE isActive = 1 LIMIT 1")  
    suspend fun getActiveRepo(): RepoMetadataEntity?  
  
    @Query("UPDATE repo_metadata SET isActive = 0")  
    suspend fun clearActiveRepo()  
  
    @Query("UPDATE repo_metadata SET isActive = 1 WHERE id = :id")  
    suspend fun setActiveRepo(id: Long)  
  
    @Query("UPDATE repo_metadata SET lastSyncAt = :time, totalCommits = :commits, diskUsageBytes = :bytes WHERE id = :id")  
    suspend fun updateSyncStats(id: Long, time: Long, commits: Int, bytes: Long)  
}



package com.example.gitphos.data.local.db.dao  
  
import androidx.room.*  
import com.example.gitphos.data.local.db.entity.SyncHistoryEntity  
import kotlinx.coroutines.flow.Flow  
  
@Dao  
interface SyncHistoryDao {  
  
    @Insert(onConflict = OnConflictStrategy.REPLACE)  
    suspend fun insert(entry: SyncHistoryEntity): Long  
  
    @Query("SELECT * FROM sync_history WHERE repoId = :repoId ORDER BY syncedAt DESC")  
    fun observeByRepo(repoId: Long): Flow<List<SyncHistoryEntity>>  
  
    @Query("SELECT * FROM sync_history WHERE repoId = :repoId ORDER BY syncedAt DESC LIMIT 1")  
    suspend fun getLastSync(repoId: Long): SyncHistoryEntity?  
  
    @Query("SELECT * FROM sync_history ORDER BY syncedAt DESC LIMIT :limit")  
    suspend fun getRecent(limit: Int = 20): List<SyncHistoryEntity>  
  
    @Query("DELETE FROM sync_history WHERE repoId = :repoId")  
    suspend fun clearForRepo(repoId: Long)  
}


package com.example.gitphos.data.local.db.dao  
  
import androidx.room.*  
import com.example.gitphos.data.local.db.entity.UploadQueueEntity  
import kotlinx.coroutines.flow.Flow  
  
@Dao  
interface UploadQueueDao {  
  
    @Insert(onConflict = OnConflictStrategy.REPLACE)  
    suspend fun insert(item: UploadQueueEntity): Long  
  
    @Update  
    suspend fun update(item: UploadQueueEntity)  
  
    @Delete  
    suspend fun delete(item: UploadQueueEntity)  
  
    @Query("SELECT * FROM upload_queue WHERE repoId = :repoId ORDER BY addedAt ASC")  
    fun observeByRepo(repoId: Long): Flow<List<UploadQueueEntity>>  
  
    @Query("SELECT * FROM upload_queue WHERE status = 'PENDING' ORDER BY addedAt ASC")  
    suspend fun getPendingItems(): List<UploadQueueEntity>  
  
    @Query("UPDATE upload_queue SET status = :status, errorMessage = :error WHERE id = :id")  
    suspend fun updateStatus(id: Long, status: String, error: String? = null)  
  
    @Query("UPDATE upload_queue SET retryCount = retryCount + 1 WHERE id = :id")  
    suspend fun incrementRetry(id: Long)  
  
    @Query("DELETE FROM upload_queue WHERE status = 'DONE'")  
    suspend fun clearCompleted()  
  
    @Query("UPDATE upload_queue SET status = 'IN_PROGRESS' WHERE id = :id")  
    suspend fun markInProgress(id: Long)  
  
    @Query("UPDATE upload_queue SET status = 'COMPLETED' WHERE id = :id")  
    suspend fun markCompleted(id: Long)  
  
    @Query("UPDATE upload_queue SET status = 'FAILED', errorMessage = :reason WHERE id = :id")  
    suspend fun markFailed(id: Long, reason: String)  
}
```

```
package com.example.gitphos.data.local.db.entity  
  
import androidx.room.Entity  
import androidx.room.PrimaryKey  
  
@Entity(tableName = "upload_queue")  
data class UploadQueueEntity(  
    @PrimaryKey(autoGenerate = true) val id: Long = 0,  
    val repoId: Long,  
    val filePath: String,  
    val status: String,       // PENDING | IN_PROGRESS | DONE | FAILED  
    val retryCount: Int = 0,  
    val addedAt: Long = System.currentTimeMillis(),  
    val errorMessage: String? = null  
)

package com.example.gitphos.data.local.db.entity  
  
import androidx.room.Entity  
import androidx.room.PrimaryKey  
  
@Entity(tableName = "sync_history")  
data class SyncHistoryEntity(  
    @PrimaryKey(autoGenerate = true) val id: Long = 0,  
    val repoId: Long,  
    val commitHash: String?,  
    val filesChanged: Int,  
    val status: String,       // SUCCESS | FAILED  
    val triggeredBy: String,  // MANUAL | AUTO  
    val syncedAt: Long = System.currentTimeMillis(),  
    val errorMessage: String? = null  
)


package com.example.gitphos.data.local.db.entity  
  
import androidx.room.Entity  
import androidx.room.PrimaryKey  
  
@Entity(tableName = "repo_metadata")  
data class RepoMetadataEntity(  
    @PrimaryKey(autoGenerate = true) val id: Long = 0,  
    val name: String,  
    val localPath: String,  
    val remoteUrl: String,  
    val branch: String = "main",  
    val isActive: Boolean = false,  
    val lastSyncAt: Long? = null,  
    val totalCommits: Int = 0,  
    val diskUsageBytes: Long = 0  
)
```


[^1]

[^1]: Feature Steps
	13Start destination logic — check if token exists on launch, skip Auth if already logged in
	14WorkManager trigger wiring — connect Sync screen to actual `SyncWorker`
	15Error handling polish — network errors, storage permission errors
	16Android permissions — `READ_MEDIA_IMAGES` for picker, `POST_NOTIFICATIONS` for WorkManager
	17Edge cases — empty states, no repo set, no internet
	18Testing — ViewModel unit tests
	19Release build config — ProGuard, signing
