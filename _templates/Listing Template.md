---
# ── Identity ─────────────────────────────────────────────────────────
title: <% tp.file.title %>
address: <% tp.file.title %>
location: []
# location: [39.7392, -104.9847]  ← right-click pin in Google Maps → "What's here?" → copy coords
neighborhood: ""

# ── Classification ───────────────────────────────────────────────────
type: apartment
# type options: apartment | house | condo | townhouse | duplex | studio | basement

status: active
# status options: active | viewing | applied | offer | leased | rejected | archived

# ── Size & Price ─────────────────────────────────────────────────────
beds: 
baths: 
sqft: 
rent: 

# ── Fees ─────────────────────────────────────────────────────────────
deposit: 
application_fee: 
pet_fee: 0
parking_fee: 0

# ── Features ─────────────────────────────────────────────────────────
parking: none
# parking options: none | street | covered | garage | carport | attached

laundry: in-unit
# laundry options: none | shared | in-unit | hookups

utilities_included: []
# options: water | trash | electric | gas | internet | heat

features: []
# options: yard | dishwasher | ac | balcony | storage | gym | pool | fireplace | basement | fenced

# ── Contact ──────────────────────────────────────────────────────────
owner: ""
management: ""
phone: ""
email: ""

# ── Tracking ─────────────────────────────────────────────────────────
link: ""
source: ""
# source options: zillow | apartments | realtor | craigslist | facebook | referral | other

date_listed: 
date_viewed: 
date_applied: 
available_date: 
lease_term: 12

# ── Analysis ─────────────────────────────────────────────────────────
commute_mins: 
rating: 
# rating: 1–5

# ── Meta ─────────────────────────────────────────────────────────────
tags:
  - type/listing
  - status/active
created: <% tp.date.now("YYYY-MM-DD") %>
---

# <% tp.file.title %>

> [!info] Quick Facts
> **Type:** `=this.type` | **Status:** `=this.status` | **Available:** `=this.available_date` | **Lease:** `=this.lease_term` mo
> **Source:** [View Listing](`=this.link`) | **Listed:** `=this.date_listed`

---

## Costs

| Fee | Amount |
| :-- | -----: |
| Rent | $`=this.rent` /mo |
| Deposit | $`=this.deposit` |
| Application Fee | $`=this.application_fee` |
| Pet Fee | $`=this.pet_fee` |
| Parking | $`=this.parking_fee` /mo |
| **Est. Move-In Total** | **$`=(this.deposit + this.application_fee)`** |

---

## Features

| Feature | Detail |
| :------ | :----- |
| Parking | `=this.parking` |
| Laundry | `=this.laundry` |
| Utilities Included | `=this.utilities_included` |
| Amenities | `=this.features` |

---

## Contact

| | |
| :-- | :-- |
| Owner | `=this.owner` |
| Management | `=this.management` |
| Phone | `=this.phone` |
| Email | `=this.email` |

---

## Commute Analysis

- **Estimated Drive:** `=this.commute_mins` min
- **Route Notes:** 
- **Parking at Work:** 

> [!tip] Get Drive Time
> Paste the address into Google Maps with your work address as destination. Check 8–9 AM Tuesday–Thursday for realistic rush hour time. Log it in `commute_mins` above.

---

## Notes

<% tp.file.cursor() %>

---

> [!question]- Questions to Ask
> - [ ] Is the listed rent negotiable?
> - [ ] What is the renewal policy and expected rent increase?
> - [ ] Are pets allowed? Breed/weight restrictions?
> - [ ] Which appliances are included?
> - [ ] Any planned construction or building changes nearby?
> - [ ] How are maintenance requests handled?
> - [ ] Is month-to-month available after the initial term?
> - [ ] What is the notice period to vacate?

---

## Timeline

- [ ] Schedule viewing — `=this.phone` 📅 
- [ ] Visit property
- [ ] Request application
- [ ] Submit application (fee: $`=this.application_fee`) 📅 
- [ ] Follow up if no response in 48 hrs 📅 
