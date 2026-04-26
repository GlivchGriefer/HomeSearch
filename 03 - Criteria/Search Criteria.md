---
title: Search Criteria
tags:
  - type/criteria
  - status/active

# ── Location ─────────────────────────────────────────────────────────
work_address: "200 E Colfax Ave, Denver, CO 80203"
target_areas: []
max_commute_mins: 
search_radius_miles: 

# ── Budget ────────────────────────────────────────────────────────────
rent_min: 
rent_max: 
deposit_max: 
total_move_in_max: 

# ── Size ──────────────────────────────────────────────────────────────
beds_min: 
beds_max: 
baths_min: 
sqft_min: 

# ── Property ─────────────────────────────────────────────────────────
type_preferred: []
# options: apartment | house | condo | townhouse | duplex | studio

# ── Pets ──────────────────────────────────────────────────────────────
has_pets: false
pet_type: ""
pet_weight_lbs: 

# ── Timeline ──────────────────────────────────────────────────────────
available_by: ""
lease_term_preferred: 12
month_to_month_ok: false

# ── Deal Breakers ─────────────────────────────────────────────────────
deal_breakers: []

# ── Must Haves ────────────────────────────────────────────────────────
must_haves: []
---

# Search Criteria

> [!important] This Is My Source of Truth
> When asking me to search on your behalf, I reference this note to filter results. Keep it updated — especially `work_address`, `rent_max`, and `must_haves`.

---

## Location

| Setting | Value |
| :------ | :---- |
| Work Address | `=this.work_address` |
| Target Areas | `=this.target_areas` |
| Max Commute | `=this.max_commute_mins` min |
| Search Radius | `=this.search_radius_miles` mi |

---

## Budget

| | |
| :-- | --: |
| Monthly Rent Range | $`=this.rent_min` – $`=this.rent_max` |
| Max Deposit | $`=this.deposit_max` |
| Max Move-In Total | $`=this.total_move_in_max` |

---

## Size & Type

| Setting | Value |
| :------ | :---- |
| Bedrooms | `=this.beds_min` – `=this.beds_max` |
| Bathrooms | `=this.baths_min`+ |
| Min Square Footage | `=this.sqft_min` sqft |
| Preferred Types | `=this.type_preferred` |

---

## Must-Haves

> [!important] Required Features
> Update the `must_haves` YAML field above. These are used to filter out listings automatically.

`=this.must_haves`

---

## Deal-Breakers

> [!danger] Reject If Any of These Are True
> Update the `deal_breakers` YAML field above.

`=this.deal_breakers`

---

## Pets

| Setting | Value |
| :------ | :---- |
| Has Pets | `=this.has_pets` |
| Type | `=this.pet_type` |
| Weight | `=this.pet_weight_lbs` lbs |

---

## Timeline

| Setting | Value |
| :------ | :---- |
| Available By | `=this.available_by` |
| Preferred Lease | `=this.lease_term_preferred` months |
| Month-to-Month OK | `=this.month_to_month_ok` |

---

## AI Search Prompt

When you want me to search, copy and paste this block into a message:

```
Search for rentals matching my criteria in [[Search Criteria]].
Source: [Zillow / Apartments.com / Realtor / Craigslist]
Additional filters this session: 
Number of results to add: 
```

I will create individual notes in `01 - Listings/` using the Listing Template, prefilled with all available data from the listing.

---

## Weighting Guide

Use this to compare close calls:

| Priority | Factor |
| :------- | :----- |
| 1 — Critical | Commute time, rent within budget, deal-breakers clear |
| 2 — High | Must-haves met, available by move-in date |
| 3 — Medium | Neighborhood feel, natural light, storage |
| 4 — Nice | Amenities, modern finishes, views |
| 5 — Bonus | Price negotiability, landlord responsiveness |
