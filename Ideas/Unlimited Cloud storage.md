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