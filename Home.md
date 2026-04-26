---
title: Home Search Dashboard
tags:
  - type/dashboard
work_address: 200 E Colfax Ave, Denver, CO 80203
budget_max: "3000"
target_move_date: 5/25/2026
search_active: true
---
		
# Home Search Dashboard

> [!info] Setup
> Work address set to CO State Capitol, Denver, CO. Update `budget_max` and `target_move_date` to enable full AI search filtering.

---

## Status Overview

```dataview
TABLE WITHOUT ID status AS "Status", length(rows) AS "Count", min(rows.rent) AS "Min $/mo", max(rows.rent) AS "Max $/mo"
FROM "01 - Listings"
WHERE contains(tags, "type/listing")
GROUP BY status
SORT rows[0].status ASC
```

---

## Map

> [!tip]+ Commute Buffer — How To
> 1. Open the full Map View panel (ribbon icon)
> 2. Type your work address in the search bar to jump to it
> 3. Use the query filter `prop:status=active` to show only live listings
> 4. Click any pin → opens the listing note with full details and costs
> 5. From a listing pin, copy the address into Google Maps to compare routes

```mapview
{"name":"All Listings","mapZoom":11,"centerLat":39.7392,"centerLng":-104.9847,"query":"path:\"01 - Listings\"","chosenMapSource":0}
```

> [!info] Map Center
> Centered on CO State Capitol, Denver, CO (work address).

---

> [!abstract]- All Listings — BASE
> ```dataview
> TABLE address AS "Address", rent AS "$/mo", beds AS "Bd", baths AS "Ba", sqft AS "SqFt", status AS "Status", commute_mins AS "Drive (min)", rating AS "⭐", source AS "Source"
> FROM "01 - Listings"
> WHERE contains(tags, "type/listing")
> SORT status ASC, rent ASC
> ```

---

> [!success]- Applied / Offer Stage
> ```dataview
> TABLE address AS "Address", rent AS "$/mo", date_applied AS "Applied", owner AS "Owner / Mgmt", phone AS "Phone", link AS "Link"
> FROM "01 - Listings"
> WHERE contains(tags, "type/listing") AND (status = "applied" OR status = "offer")
> SORT date_applied DESC
> ```

---

> [!example]- Viewing Queue
> ```dataview
> TABLE address AS "Address", rent AS "$/mo", available_date AS "Available", phone AS "Phone", rating AS "⭐"
> FROM "01 - Listings"
> WHERE contains(tags, "type/listing") AND status = "viewing"
> SORT rating DESC
> ```

---

## Navigation

| | |
| :-- | :-- |
| [[00 - Pipeline\|Pipeline Board]] | Kanban — drag listings through stages |
| [[Commute Map]] | Leaflet radius map from work address |
| [[Search Criteria]] | My requirements — update before AI searches |
| [[README|Vault Documentation]] | Plugin guide, YAML reference, workflows |
| [[Patch Notes]] | Change log |

---

## Search Sources

| Source | Best For | Note |
| :----- | :------- | :--- |
| [[Zillow]] | Rentals + for-sale, rich filters | Strong map search |
| [[Apartments.com]] | Rental aggregator | Best filter depth |
| [[Realtor.com]] | MLS-connected accuracy | Good for new listings |
| [[Craigslist]] | Direct landlord deals | Lower fees, higher noise |
| [[Facebook Marketplace]] | Private owners | Negotiate directly |

---

> [!todo]- Open Tasks Across All Listings
> ```tasks
> path includes 01 - Listings
> not done
> ```

---

> [!question]- Notes & Questions to Resolve
> ```dataview
> LIST
> FROM "01 - Listings"
> WHERE contains(tags, "type/listing") AND status = "active"
> SORT rating DESC
> LIMIT 10
> ```
