<p align="center">
  <img src="assets/logo.png" alt="Plateful Logo" width="150" height="150">
</p>

<p align="center">
  <img src="assets/banners/plateful-banner.png" alt="Plateful Banner" width="75%">
</p>

<h1 align="center">Plateful – iOS Food Donation Platform</h1>

<p align="center">
  A streamlined mobile solution for connecting donors with NGOs, enabling efficient food donation management, scheduling, and verification.
</p>

<p align="center">
  <a href="#features"><img src="https://img.shields.io/badge/Platform-iOS-blue?style=for-the-badge"></a>
  <a href="#architecture"><img src="https://img.shields.io/badge/Architecture-MVC-green?style=for-the-badge"></a>
  <a href="#backend"><img src="https://img.shields.io/badge/Backend-Firebase-orange?style=for-the-badge"></a>
  <a href="https://cloudinary.com"><img src="https://img.shields.io/badge/Images-Cloudinary-lightgrey?style=for-the-badge"></a>
  <a><img src="https://img.shields.io/badge/Swift-5.0+-f05138?style=






# Plateful – Food Donation Mobile Application
Smart food donation and NGO coordination system built for iOS.

---

## 1. Project Overview
Plateful is an iOS mobile application designed to connect donors with NGOs to simplify the food donation process. The system enables:

- Donors to create donations, upload item images, schedule pickups, and track donation status.
- NGOs to accept donations, view details, schedule pickups, and update delivery progress.
- Admins to verify NGOs, manage platform data, and oversee system activity.

The application follows the MVC architecture, uses Firebase for authentication and storage, Cloudinary for image uploads, and GitHub for version control.

---

## 2. Team Roles and Modules

### Person 1 – Authentication + Profile
- Splash, Login, Signup
- View Profile / Edit Profile
- Firebase Authentication setup

### Person 2 – Donor Home + Donation History
- Donor Home screen
- Donation History List
- Donation History Detail
- Firestore structure for “donations” + “history”

### Person 3 – NGO Discovery + Favorites
- NGO List
- Search
- NGO Profile
- Favorites
- Firestore NGO sample data

### Person 4 – Add Donation + Status Tracking
- Add Donation steps
- Confirmation screen
- Donation Status
- Cloudinary upload configuration

### Person 5 – NGO Collector + Pickup Scheduling
- NGO Home
- Available Donations
- Accept Donation
- Pickup Scheduling
- Firestore scheduling fields + status design

### Person 6 – Admin + Notifications + Legal + GitHub
- Admin Dashboard
- NGO Verification
- Notifications screen
- FAQ, Terms, Privacy pages
- GitHub repository, branches, README, documentation

---

## 3. Technologies Used
- Swift (UIKit, Storyboards)
- Firebase Authentication
- Firebase Firestore
- Cloudinary (image hosting)
- GitHub (version control)
- MVC Architecture
- AutoLayout for responsive UI

---

## 4. Project Architecture

### MVC (Model–View–Controller)
- **Models**: Firestore documents, data structures
- **Views**: UIKit Storyboard screens
- **Controllers**: ViewControllers managing logic and UI

### Recommended Folder Structure
```
/Controllers
/Views
/Models
/Services (Firebase, Cloudinary)
/Resources (Assets, Icons)
```

---

## 5. Git Workflow & Branching Strategy

### Main Branches
- `main` → stable release for submission
- `dev` → integration branch

### Feature Branches
```
feature/person1-auth-profile
feature/person2-donor-home-history
feature/person3-ngo-discovery-favorites
feature/person4-add-donation-status
feature/person5-ngo-collector-scheduling
feature/person6-admin-notifications-legal
```

### Workflow Rules
- No direct commits to `main`.
- Each member works only in their feature branch.
- When ready, create a Pull Request into `dev`.
- After testing, `dev` merges into `main`.

---

## 6. Firestore Data Models (Backend Design)

### 6.1 Users Collection (`users`)
```
id: string
name: string
email: string
role: "donor" | "ngo" | "admin"
createdAt: timestamp
```

---

### 6.2 NGOs Collection (`ngos`)
```
id: string
name: string
licenseNumber: string
location: string
contactEmail: string
description: string
approved: boolean
createdAt: timestamp
```

Admin actions:
- View pending NGOs where `approved == false`
- Approve or reject NGO applications

---

### 6.3 Donations Collection (`donations`)
```
donorId: string
ngoId: string | null
items: array
images: array (Cloudinary URLs)
pickupTime: timestamp
status: "Pending" | "Accepted" | "Scheduled" | "Completed" | "Cancelled"
createdAt: timestamp
```

---

### 6.4 Notifications Collection (`notifications`)
```
title: string
body: string
type: "message" | "announcement" | "system"
targetRole: "donor" | "ngo" | "admin" | "all"
createdAt: timestamp
```

Filtering:
- Donors see: donor + all
- NGOs see: ngo + all
- Admin sees: admin + all

---

## 7. Cloudinary Integration
- Used by Person 4 during Add Donation flow.
- User selects an image → uploaded to Cloudinary → URL returned → saved to Firestore in the donation record.

---

## 8. Legal Pages
Stored as markdown in `/documentation/`:

- `faq.md`
- `privacy-policy.md`
- `terms-and-conditions.md`

Displayed in Admin/Settings.

---

## 9. Developer Setup Instructions
1. Clone the repository:
```
git clone <repo-url>
```

2. Checkout your branch:
```
git checkout feature/personX-module
```

3. Open project in Xcode.

4. Drag `GoogleService-Info.plist` into Xcode.

5. Add Cloudinary configuration (provided by Person 4).

6. Build and run on iPhone/iPad simulator.

---

## 10. Demo Requirements
Each teammate must present:
- Their module screens
- Their backend logic
- Their technical responsibility
- Clean commit history in GitHub
- No errors or warnings
- Proper MVC structure

---

## 11. Credits
Developed by a 6-member team for the IT8108 Mobile Application Development Project.



## 📱 Screenshots

<p align="center">
  <img src="assets/screenshots/login.png" width="250">
  <img src="assets/screenshots/donor_home.png" width="250">
  <img src="assets/screenshots/ngo_list.png" width="250">
</p>

<p align="center">
  <img src="assets/screenshots/add_donation.png" width="250">
  <img src="assets/screenshots/pickup_schedule.png" width="250">
  <img src="assets/screenshots/admin_dashboard.png" width="250">
</p>

---



---

---

<p align="center">
  Developed by the Plateful Team – IT8108 Mobile Application Development Project  
  <br>
  © 2025 Plateful. All rights reserved.
</p>

