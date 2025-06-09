# SMARTPARK – Smart Parking Monitoring & Reservation System
Smart Park is a user-friendly web application that allows users to view available parking spots in real time, update parking status, and make future reservations. It aims to reduce city parking issues and save users time with smart guidance.

## Technologies Used
HTML5 & CSS3 (Responsive design using media queries)

JavaScript

Firebase (Firestore & Authentication)

Custom CSS components for modern modal and card layouts

### Key Features
### Navigation
Header: Includes Logo, Home, Location, and Map links

Search Bar: Search parking areas by location

Find Button: Displays suitable parking spots based on the search

## Dashboard (Main View)
Login & Reservation Buttons: For user login and booking a parking spot

App Introduction: Short info about ParkSmartApp with a download link

Category Cards: Cards for Shopping Malls, Hospitals, Public Parking, etc.

Useful Links: GitHub, LinkedIn, Map

Dynamic Parking Table:

Shows location, floor/block, time, and availability status

Auto-updates with data from Firebase Firestore

## Additional Sections
What is ParkSmart?: Details about the system's goal and benefits

Email Subscription: Users can sign up for the newsletter

Login Modal: Simple login form (currently for simulation)

Reservation Modal: Allows users to select location and date/time

### Firebase Integration
### Firestore Database
parkStatus: Stores current parking availability
Path: artifacts/{appId}/public/data/parkStatus

reservations: Stores each user’s individual reservations
Path: artifacts/{appId}/users/{userId}/reservations

## Authentication
Users can log in anonymously or with a custom token

Each user is assigned a unique userId

## Real-Time Updates
Uses onSnapshot to listen to changes in the parkStatus collection

Automatically updates the table when a spot becomes occupied or free

## Updating Data & Booking
A logged-in user can mark a spot (e.g., B3) as occupied

Reservation modal records the chosen location/time in the user’s reservations collection

## Setup & Development Notes
CSS: Fully custom, responsive design written with pure CSS (no external UI framework)

Firebase Setup:

Requires __firebase_config and __app_id to be defined in the environment.

If not, fallback default values will be used.

Recommended Firestore Rules:

// Public Data
match /artifacts/{appId}/public/data/{doc} {
  allow read, write: if request.auth != null;
}

// User-Specific Data
match /artifacts/{appId}/users/{userId}/{doc} {
  allow read, write: if request.auth != null && request.auth.uid == userId;
}
## User Experience
Confirmation messages shown after reservation or park status update

Simple and intuitive UI with modal forms for login and reservation

Can be expanded with advanced validations and UI enhancements

## Future Enhancements
Auto-release of parking spots after timeout (via Firebase Functions)

Real user authentication

QR code integration for check-in/out

Map API integration for location-based navigation

### To see a live demo of the project, click the link below:To see a live demo of the project, click the link below:
https://nurhayatyavuz.github.io/SmartPark/
