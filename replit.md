# DistanceIQ — Workplace Commute Analyzer

## Overview
A single-page browser tool that helps HR and real estate teams analyze employee commute distances to potential new office locations. No backend — all processing runs client-side.

## Architecture
- **index.html** — Self-contained single-file app (HTML + CSS + JS)
- **Server** — Python `http.server` on port 5000 (serves static files)

## Key Features
- Download Excel templates (Employee, Locations, ZIP Reference)
- Upload employee home addresses + current office (optional)
- Upload optional ZIP→Lat/Long reference file for geocoding fallback
- Add new candidate office locations via file upload or manual entry
- 4-tier geocoding: US Census Bureau → Zippopotam.us → Census city-level → ZIP reference file → embedded ZIP table
- Haversine straight-line distance calculation (miles)
- Commute distance matrix with color-coded results
- Top 3 location ranking by % employees within 50 miles
- Capacity allocation table with over/near-capacity alerts
- Export results to .xlsx

## Dependencies
- **xlsx.js** (CDN) — Excel read/write
- **IBM Plex Mono / IBM Plex Sans** (Google Fonts) — Typography
- US Census Geocoder API (free, no key required)
- Zippopotam.us API (free, no key required)

## Running
The app is served by Python's built-in HTTP server:
```
python3 -m http.server 5000
```
