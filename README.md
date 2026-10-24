# 🏍️ BlaBlaBikes — Nashik Bike Ride Sharing

> A local motorcycle ride-sharing web app for Nashik city. Find a co-rider heading your way, or offer a seat on your bike and split the fuel cost.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [App Pages & Views](#app-pages--views)
- [Map & Routing](#map--routing)
- [Nashik Locations Supported](#nashik-locations-supported)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

**BlaBlaBikes** is a single-page web application designed specifically for **Nashik, Maharashtra**. It connects motorcycle riders with passengers traveling similar routes across the city — enabling shared rides at a fraction of the cost.

The app runs entirely in the browser as a static HTML/CSS/JS application with no backend required. Route calculations use the **OSRM** public routing API, and maps are rendered via **Leaflet.js** with **OpenStreetMap** tiles.

---

## Features

### 🔍 Find Rides
- Search available rides by **pickup** and **drop-off** location
- Filter by **date**
- Live **route map** with turn-by-turn road polylines, markers, and route stats (distance & ETA)
- Autocomplete suggestions for Nashik localities

### 🏍️ Offer a Ride
- Post your ride with source, destination, date, time, and price
- Select your bike model, helmet availability, and seat count
- Real-time route preview on the map as you fill in locations

### 📊 Dashboard
- Quick stats overview: active rides, completed trips, total earnings
- At-a-glance performance metrics

### 💬 Coordination Chat
- In-app messaging between rider and passenger
- Quick-reply suggestions for common messages
- Real-time chat interface

### 👤 Profile Management
- View and edit profile details
- Ratings and reviews display
- Trip history

### 🔐 Authentication
- Login / Sign Up flow
- Guest browsing mode

### 🗺️ Interactive Maps
- **Leaflet.js** maps on every relevant view (search, offer, ride details)
- OSRM-powered real road routing with alternate routes
- Custom markers — CBS-style circle for pickup, red pin for drop-off
- Auto-fit bounds to show full route
- Fallback routing when OSRM is unavailable

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| **Structure** | HTML5 (single-page, semantic) |
| **Styling** | Vanilla CSS (CSS custom properties, responsive) |
| **Logic** | Vanilla JavaScript (ES5-compatible, no frameworks) |
| **Maps** | [Leaflet.js](https://leafletjs.com/) v1.9.4 |
| **Tiles** | [OpenStreetMap](https://www.openstreetmap.org/) |
| **Routing** | [OSRM](http://project-osrm.org/) (Open Source Routing Machine) |
| **Fonts** | [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) |
| **Dev Server** | Python `http.server` (no-cache wrapper) |

---

## Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Edge, Safari)
- Python 3.x (for the local dev server)

### Run Locally

```bash
# 1. Clone the repository
git clone https://github.com/Krushnaprasad3Marathe/BlaBlaaBikes.git
cd BlaBlaaBikes

# 2. Start the local server
python server.py

# 3. Open in browser
# Navigate to http://localhost:8000
```

Alternatively, you can simply open `index.html` directly in your browser — no server required for basic functionality.

---

## Project Structure

```
BlaBlaaBikes/
├── index.html            # Main application (served by default)
├── index (3).html        # Source/tracked version of the app
├── index_backup.html     # Backup copy
├── server.py             # Python dev server with cache-busting headers
├── README.md             # This file
└── .gitignore            # Git ignore rules
```

> **Note**: The entire application is contained in a single HTML file — all CSS, JavaScript, and data are embedded inline for zero-dependency deployment.

---

## App Pages & Views

| View | ID | Description |
|------|-----|-------------|
| **Home** | `view-home` | Hero banner with search bar, feature cards |
| **Dashboard** | `view-dashboard` | Stats overview with ride metrics |
| **Find Rides** | `view-search` | Search form + live route map + ride listings |
| **Ride Details** | `view-ride-details` | Full ride info, rider profile, route map, booking |
| **Offer a Ride** | `view-offer-ride` | Multi-field form to post a new ride |
| **My Rides** | `view-my-rides` | User's booked and offered rides |
| **Chat** | `view-chat` | Rider-passenger coordination messaging |
| **Profile** | `view-profile` | User profile, ratings, and settings |
| **Login** | `view-login` | Authentication form |

---

## Map & Routing

The app features an interactive map system on multiple views:

1. **Route Calculation**: Uses the [OSRM public API](https://router.project-osrm.org/) to fetch real turn-by-turn road routes between two Nashik locations.

2. **Visual Elements**:
   - 🔵 **Primary route** — bold blue polyline with navy casing
   - 🩵 **Alternate route** — light blue polyline (when available)
   - 🟢 **Pickup marker** — CSS-styled circle with label
   - 🔴 **Drop-off marker** — red pin with label
   - 📊 **Route stats** — distance (km) and estimated time (min)

3. **Fallback**: If OSRM is unreachable, a direct line with estimated distance is drawn.

---

## Nashik Locations Supported

The app includes autocomplete support for major Nashik localities:

| Area | Area | Area |
|------|------|------|
| CBS | College Road | Canada Corner |
| Panchavati | Nashik Road Station | Satpur |
| CIDCO | Gangapur Road | Indira Nagar |
| Bytco Point | Nashik Road | Mumbai Naka |
| Dwarka | Deolali Camp | Pathardi Phata |
| Rane Nagar | Makhmalabad | Govind Nagar |
| Shalimar | Tidke Colony | And more... |

---

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## License

This project is open source. Feel free to use, modify, and distribute.

---

