---
title: Zillow
tags:
  - type/source
source_type: rental
search_url: "https://www.zillow.com/homes/for_rent/"
ai_searchable: true
notes: "Strong map-based search. Has rentals and for-sale. Good price history and zestimate data."
---

# Zillow

> [!info] Source Profile
> **Type:** Rentals + For-Sale | **AI Searchable:** Yes | **Listing Quality:** High

---

## Search URL Template

```
https://www.zillow.com/homes/for_rent/{city}-{state}/{beds}-beds_beds/?price=0-{max_rent}
```

**Example — Denver rentals under $2,000, 2br+:**
```
https://www.zillow.com/homes/for_rent/Denver,-CO/2-_beds/?price=0-2000&mp=2000&doz=7&p=1
```

---

## Key Filters Available

| Filter | Notes |
| :----- | :---- |
| Price range | Min/max monthly rent |
| Beds / Baths | Exact or minimum |
| Home type | Apartment, house, condo, townhouse |
| Listed within | 1, 7, 14, 30 days |
| Pets allowed | Yes/no |
| In-unit laundry | Yes/no |
| Parking | Covered, garage |
| Square footage | Min/max |
| Keywords | Search listing text |

---

## AI Search Instructions

When asking me to search Zillow on your behalf, provide the following and I'll return matching listings formatted as new notes:

```
City/zip: 
Max rent: $
Min beds: 
Must-haves: (e.g., parking, pets ok)
Max commute: (min drive from work)
Listed within: (days)
```

---

## Notes

- [p] Strong map UI with draw-a-search-zone tool
- [p] Price history and days-on-market visible
- [c] Listings occasionally have inaccurate availability
- [c] Some listings are syndicated from management companies — contact info may be a call center
