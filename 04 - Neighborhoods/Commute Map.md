---
title: Commute Map
tags:
  - type/map
work_address: ""
work_lat: 
work_lng: 
---

# Commute Map

> [!warning] Setup Required
> Replace `work_lat` and `work_lng` in the Properties panel with your work coordinates.
> Get them: open Google Maps → search your work address → right-click the pin → copy the first two numbers (lat, lng).
> Then update those same values in the `marker` and `circle` lines inside the Leaflet block below.

---

## Radius Buffer Map

The three circles approximate drive-time zones from your work address under normal conditions:
- **Green (5 mi)** — ~10 min or less
- **Yellow (10 mi)** — ~15–20 min
- **Red (15 mi)** — ~25–35 min depending on traffic

```leaflet
id: commute-buffer-map
lat: 39.7392
long: -104.9903
height: 550px
zoom: 11
minZoom: 9
maxZoom: 17
unit: miles
scale: 1
recenter: true
darkMode: false
markerFolder: 01 - Listings
marker: default, 39.7392, -104.9903, "Work Address", "Update these coords", ""
circle: 39.7392, -104.9903, 5, "~10 min", "#2f9e44"
circle: 39.7392, -104.9903, 10, "~20 min", "#f08c00"
circle: 39.7392, -104.9903, 15, "~30 min", "#e03131"
```

> [!tip] How to Update This Map
> 1. Get your work address lat/lng from Google Maps (right-click → copy coords)
> 2. In the code block above, replace all four instances of `39.7392, -104.9903` with your real coords
> 3. The `markerFolder` line auto-pulls every listing in `01 - Listings/` that has a `location: [lat, lng]` field set

---

## Neighborhood Notes

Use this section to record impressions of areas you've scouted.

| Neighborhood | Distance to Work | Vibe | Avg Rent | Notes |
| :----------- | :--------------- | :--- | :------- | :---- |
| | | | | |

---

## Resources

- [[Home]] — Dashboard
- [[Search Criteria]] — My requirements
- [[00 - Pipeline]] — Application status board
