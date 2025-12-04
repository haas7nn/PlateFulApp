# Plateful – Food Donation Mobile App

## Overview
Plateful is an iOS mobile application that connects donors with NGOs to schedule and track food donations. Donors can discover NGOs, create donation requests, and follow their status. NGOs can accept donations and manage pickups. Admins oversee NGO verification and platform activity.

## Team Roles
- Person 1 – Authentication & Profile
- Person 2 – Donor Home & Donation History
- Person 3 – NGO Discovery & Favorites
- Person 4 – Add Donation & Status Tracking
- Person 5 – NGO Collector & Scheduling
- Person 6 – Admin, Notifications, GitHub & Documentation

## Technologies
- Swift (UIKit, Storyboards)
- Firebase Authentication
- Firebase Firestore
- Cloudinary (image storage)
- GitHub (version control)

## Architecture
The app follows the Model–View–Controller (MVC) architecture and uses AutoLayout for responsive design on iPhone and iPad.

## Branching Strategy
- `main` – Stable release (demo-ready)
- `dev` – Integration branch
- `feature/personX-...` – Individual feature branches

## Backend Structure (High-Level)
- `users` – All app users (Donor, NGO, Admin)
- `ngos` – NGO profiles and verification status
- `donations` – Donation records and status updates
- `notifications` – System and user notifications
