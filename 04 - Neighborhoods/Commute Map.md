---
title: Commute Map
tags:
  - type/map
work_address: "200 E Colfax Ave, Denver, CO 80203"
work_lat: 39.7392
work_lng: -104.9847
---

# Commute Map

> [!info] Work Address
> Anchored to **200 E Colfax Ave, Denver, CO 80203** — `[39.7392, -104.9847]`

---

## Radius Buffer Map

The three circles approximate drive-time zones from your work address under normal conditions:
- **Green (5 mi)** — ~10 min or less
- **Yellow (10 mi)** — ~15–20 min
- **Red (15 mi)** — ~25–35 min depending on traffic

```leaflet
id: commute-buffer-map
lat: 39.7392
long: -104.9847
height: 550px
zoom: 11
minZoom: 9
maxZoom: 17
unit: miles
scale: 1
recenter: true
darkMode: false
markerFolder: 01 - Listings
marker: default, 39.7392, -104.9847, "CO State Capitol — Work", "Denver, CO 80203", ""
overlay:
  - ['#2f9e44', [39.7392, -104.9847], 5 miles, '~10 min']
  - ['#f08c00', [39.7392, -104.9847], 10 miles, '~20 min']
  - ['#e03131', [39.7392, -104.9847], 15 miles, '~30 min']
```

> [!tip] Adding Listings to the Map
> Set `location: [lat, lng]` in any listing note's YAML — the `markerFolder` line auto-pulls every note in `01 - Listings/` that has that field set.

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
