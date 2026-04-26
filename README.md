# 🏠 HomeSearch Vault

![Obsidian](https://img.shields.io/badge/Obsidian-v1.11%2B-7C3AED?style=flat-square&logo=obsidian&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-AI_Search-D97706?style=flat-square&logo=anthropic&logoColor=white)
![Dataview](https://img.shields.io/badge/Dataview-v0.5.68-4A90D9?style=flat-square)
![Templater](https://img.shields.io/badge/Templater-v2.19.3-4A90D9?style=flat-square)
![Map View](https://img.shields.io/badge/Map_View-v6.1.4-4A90D9?style=flat-square)
![Kanban](https://img.shields.io/badge/Kanban-v2.0.51-4A90D9?style=flat-square)
![Tasks](https://img.shields.io/badge/Tasks-v7.23.1-4A90D9?style=flat-square)
![Leaflet](https://img.shields.io/badge/Leaflet-v6.0.5-4A90D9?style=flat-square)
![Status](https://img.shields.io/badge/status-active-2f9e44?style=flat-square)

**A structured rental search system built in Obsidian — with AI-powered listing discovery via Claude Code in VS Code.**

Track listings from multiple sources, analyze commute times on an interactive map, manage your application pipeline, and let Claude search and populate your database automatically.

---

## Table of Contents

- [What Is This?](#what-is-this)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Plugin Reference](#plugin-reference)
- [Usage](#usage)
  - [Adding a Listing](#adding-a-listing)
  - [AI Search with Claude Code](#ai-search-with-claude-code-in-vs-code)
  - [Commute Analysis](#commute-analysis)
  - [Managing the Pipeline](#managing-the-pipeline)
- [Vault Structure](#vault-structure)
- [YAML Field Reference](#yaml-field-reference)
- [Status Lifecycle](#status-lifecycle)
- [Dataview Query Reference](#dataview-query-reference)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Changelog](#changelog)

---

## What Is This?

HomeSearch is an Obsidian vault template for managing a real estate or rental search. Every property is a structured note with ~30 standardized YAML fields. Those fields power:

- **Dataview tables** — live-queried dashboards that sort, filter, and aggregate listings automatically
- **Map View pins** — every listing with a `location: [lat, lng]` field appears as a pin on an embedded map
- **Leaflet radius maps** — commute buffer circles drawn around your work address
- **Kanban pipelines** — drag listings through Active → Viewing → Applied → Offer → Leased
- **Tasks tracking** — due dates on viewing appointments and application deadlines
- **AI-assisted ingestion** — Claude Code reads your search criteria and creates listing notes from live web searches, no copy-paste required

---

## Features

- **One-command listing creation** via QuickAdd — address prompt → fully templated note in `01 - Listings/`
- **Auto-populated fields** via Templater — title, address, and creation date filled on note creation
- **Live dashboard** (`Home.md`) with status stats, embedded map, and collapsible full listing table
- **Commute radius map** with 5 / 10 / 15 mile rings anchored to your work address
- **Application pipeline** Kanban board showing rent, beds, commute time, and star rating on each card
- **Search source reference notes** for Zillow, Apartments.com, Realtor.com, Craigslist, and Facebook Marketplace — with URL templates and filter cheatsheets
- **AI bulk search** — ask Claude Code to search any supported site and auto-create listing notes
- **Move-in cost calculator** in each listing note (deposit + application fee)
- **Questions checklist** and timeline task list built into every listing

---

## Prerequisites

- [Obsidian](https://obsidian.md) v1.11 or later
- [Claude Code](https://claude.ai/code) (CLI or VS Code extension) — for AI-assisted search
- Git — to clone this repo

---

## Installation

```bash
git clone https://github.com/your-username/HomeSearch.git
```

1. Open Obsidian → **Open folder as vault** → select the cloned `HomeSearch/` directory
2. When prompted about community plugins, click **Trust author and enable plugins**
3. All plugins are pre-installed and pre-configured — no manual downloads needed
4. Open **Settings → Community Plugins** and confirm all 11 plugins show as enabled

### First-Time Configuration

After opening the vault, complete these one-time steps:

| Step | Where | What to Set |
| :--- | :---- | :---------- |
| 1 | `03 - Criteria/Search Criteria.md` → Properties | Your budget, bed count, must-haves, work address |
| 2 | `Home.md` → Properties | `work_address`, `budget_max`, `target_move_date` |
| 3 | `04 - Neighborhoods/Commute Map.md` | Replace the 4 coordinate instances with your work lat/lng |
| 4 | `Home.md` mapview code block | Update `centerLat` / `centerLng` to your search area |
| 5 | Settings → Hotkeys | Bind `QuickAdd: New Listing` to `Cmd+Shift+N` |

**Getting coordinates:** open [Google Maps](https://maps.google.com) → right-click any location → click the coordinates at the top of the context menu to copy them.

---

## Plugin Reference

All plugins are bundled in `.obsidian/plugins/` and listed in `community-plugins.json`. No manual installation needed.

### Core Functionality

| Plugin | Version | Role |
| :----- | :------ | :--- |
| [Dataview](https://github.com/blacksmithgu/obsidian-dataview) | v0.5.68 | Live tables, stats, and queries on the dashboard |
| [Map View](https://github.com/esm7/obsidian-map-view) | v6.1.4 | Embedded interactive map — listing pins from `location` field |
| [Templater](https://github.com/SilentVoid13/Templater) | v2.19.3 | Auto-fills title, date, cursor on new listing notes |
| [QuickAdd](https://github.com/chhoumann/quickadd) | v2.12.0 | "New Listing" command — address prompt → note in `01 - Listings/` |
| [Homepage](https://github.com/mirnovov/obsidian-homepage) | v4.4.0 | Opens `Home.md` automatically on Obsidian startup |

### Pipeline & Tracking

| Plugin | Version | Role |
| :----- | :------ | :--- |
| [Kanban](https://github.com/mgmeyers/obsidian-kanban) | v2.0.51 | Drag-and-drop pipeline board with linked listing metadata |
| [Tasks](https://github.com/obsidian-tasks-group/obsidian-tasks) | v7.23.1 | Due dates and recurrence on viewing/application checklist items |
| [Obsidian Leaflet](https://github.com/javalent/obsidian-leaflet) | v6.0.5 | Radius buffer map with custom distance rings from work address |

### Visual

| Plugin | Version | Role |
| :----- | :------ | :--- |
| [Banners](https://github.com/noatpad/obsidian-banners) | v1.3.3 | Header images and icons on notes |
| [Iconize](https://github.com/FlorianWoelki/obsidian-iconize) | v2.14.7 | Folder and file icons in the sidebar |
| [Ink](https://github.com/daledesilva/obsidian_ink) | v0.3.4 | Freehand annotation on notes |

---

## Usage

### Adding a Listing

**Method 1 — QuickAdd (recommended)**

1. `Cmd+Shift+N` (or `Cmd+P` → "New Listing")
2. Type the property address → Enter
3. Note opens in `01 - Listings/` with template applied and cursor ready
4. Fill YAML fields in the Properties panel
5. Paste `[lat, lng]` into the `location` field for the map pin

**Method 2 — Manual**

Create any note inside `01 - Listings/` — Templater fires automatically on creation.

**Method 3 — AI (see below)**

---

### AI Search with Claude Code in VS Code

This vault is designed to work with [Claude Code](https://claude.ai/code) running inside VS Code with the vault folder as the open workspace. Claude can read your criteria, search listing sites live, and write new notes directly into `01 - Listings/` — no copy-paste needed.

#### Setup

1. Install the **Claude Code extension** in VS Code
2. Open the `HomeSearch/` vault folder in VS Code (`File → Open Folder`)
3. Open the Claude Code panel (`Cmd+Esc` or the sidebar icon)
4. Claude now has full read/write access to your vault files

#### Example Prompts

**Bulk search from criteria:**
```
Search Apartments.com for rentals matching my criteria in 03 - Criteria/Search Criteria.md.
Add the top 5 results as listing notes in 01 - Listings/.
```

**Targeted search with overrides:**
```
Search Zillow for 2br apartments in Lakewood CO under $1,800/mo with in-unit laundry.
Create notes for any not already in 01 - Listings/.
```

**Check a specific listing:**
```
Check if the listing at [address] is still available on Zillow and update its status in the note.
```

**Batch availability check:**
```
Check all listings in 01 - Listings/ where status = "active" and update any that have changed.
```

**Add from a copied listing:**
```
Create a listing note from this: [paste listing text from Facebook Marketplace or any site]
```

#### How It Works

Claude reads `03 - Criteria/Search Criteria.md` to understand your requirements, uses its web search tool to query the specified site, extracts the relevant listing fields, and writes a fully-formatted note using the schema in `_templates/Listing Template.md`. The note appears immediately in your vault — open Obsidian and it's already pinned on the map.

> **Note:** Facebook Marketplace requires login and cannot be searched directly. Paste listing text to Claude instead — it will format and create the note for you.

---

### Commute Analysis

1. Open `04 - Neighborhoods/Commute Map.md`
2. The Leaflet map shows all listings as pins with three distance rings:
   - 🟢 **5 mi** — approx. 10 min or less
   - 🟡 **10 mi** — approx. 15–20 min
   - 🔴 **15 mi** — approx. 25–35 min
3. For any listing you're serious about, get a precise time:
   - Google Maps → origin: listing address → destination: work address
   - Depart at **Tuesday 8:15 AM** for realistic rush-hour timing
   - Enter the result in `commute_mins` on the listing note
4. The `Home.md` BASE table shows `commute_mins` alongside rent for side-by-side comparison

---

### Managing the Pipeline

Open `00 - Pipeline.md` in Kanban view. Each card is a link to a listing note — drag it between lanes as the status changes.

| Lane | Status Value | Trigger |
| :--- | :----------- | :------ |
| Active | `active` | Listing found |
| Viewing Scheduled | `viewing` | Tour booked |
| Applied | `applied` | Application submitted |
| Offer / Negotiating | `offer` | Back-and-forth with landlord |
| Archive | `leased` / `rejected` | Outcome reached |

When you move a card, also update the `status` field in the listing note's YAML so Dataview tables stay accurate.

---

## Vault Structure

```
HomeSearch/
├── README.md                      ← This file
├── Home.md                        ← Dashboard (opens on startup)
├── 00 - Pipeline.md               ← Kanban application pipeline
├── 01 - Listings/                 ← One note per property
├── 02 - Search Sources/
│   ├── Zillow.md
│   ├── Apartments.com.md
│   ├── Realtor.com.md
│   ├── Craigslist.md
│   └── Facebook Marketplace.md
├── 03 - Criteria/
│   └── Search Criteria.md         ← Source of truth for AI searches
├── 04 - Neighborhoods/
│   └── Commute Map.md             ← Leaflet radius map from work address
├── 05 - Archive/                  ← Move rejected/expired listings here
├── Resources/
│   ├── Style Guide.md
│   └── Patch Notes.md
└── _templates/
    └── Listing Template.md        ← Templater-powered note schema
```

---

## YAML Field Reference

Every listing note in `01 - Listings/` uses this schema. Keep numeric fields (`rent`, `deposit`, `application_fee`) as plain numbers — no `$` sign — so Dataview can do math on them.

| Field | Type | Description |
| :---- | :--- | :---------- |
| `title` | string | Auto-filled from filename (Templater) |
| `address` | string | Full street address |
| `location` | `[lat, lng]` | Coordinates — required for map pins |
| `neighborhood` | string | Area name — used in Dataview grouping |
| `type` | enum | `apartment` `house` `condo` `townhouse` `duplex` `studio` `basement` |
| `status` | enum | `active` `viewing` `applied` `offer` `leased` `rejected` `archived` |
| `beds` | number | Bedroom count |
| `baths` | number | Bathroom count (0.5 increments ok) |
| `sqft` | number | Square footage |
| `rent` | number | Monthly rent (no `$`) |
| `deposit` | number | Security deposit |
| `application_fee` | number | One-time application fee |
| `pet_fee` | number | Monthly pet fee (0 if none) |
| `parking_fee` | number | Monthly parking fee (0 if included) |
| `parking` | enum | `none` `street` `covered` `garage` `carport` `attached` |
| `laundry` | enum | `none` `shared` `in-unit` `hookups` |
| `utilities_included` | list | `[water, trash, electric, gas, internet, heat]` |
| `features` | list | `[yard, dishwasher, ac, balcony, storage, gym, pool, fireplace, fenced]` |
| `owner` | string | Landlord name |
| `management` | string | Property management company |
| `phone` | string | Contact phone |
| `email` | string | Contact email |
| `link` | string | URL to original listing |
| `source` | enum | `zillow` `apartments` `realtor` `craigslist` `facebook` `referral` `other` |
| `date_listed` | date | `YYYY-MM-DD` — when first posted |
| `date_viewed` | date | When you toured |
| `date_applied` | date | When you submitted |
| `available_date` | date | Move-in availability |
| `lease_term` | number | Months (default 12) |
| `commute_mins` | number | Drive time to work in minutes |
| `rating` | number | Your rating 1–5 |
| `created` | date | Auto-filled by Templater |

---

## Status Lifecycle

```
active ──→ viewing ──→ applied ──→ offer ──→ leased
               │                      │
               └──→ rejected           └──→ rejected
                        │
                        └──→ archived
```

---

## Dataview Query Reference

These are the queries powering the dashboard. Copy them into any note.

**All active listings by rent:**
```dataview
TABLE address, rent, beds, baths, commute_mins, rating
FROM "01 - Listings"
WHERE contains(tags, "type/listing") AND status = "active"
SORT rent ASC
```

**Status summary with rent range:**
```dataview
TABLE WITHOUT ID status AS "Status", length(rows) AS "Count", min(rows.rent) AS "Min", max(rows.rent) AS "Max"
FROM "01 - Listings"
WHERE contains(tags, "type/listing")
GROUP BY status
```

**Within budget, best rated first:**
```dataview
TABLE address, rent, beds, commute_mins, rating
FROM "01 - Listings"
WHERE contains(tags, "type/listing") AND rent <= [[Search Criteria]].rent_max
SORT rating DESC
```

**Open tasks across all listings:**
```tasks
path includes 01 - Listings
not done
```

---

## Keyboard Shortcuts

| Action | Default |
| :----- | :------ |
| New Listing | Assign in Settings → Hotkeys (`Cmd+Shift+N` recommended) |
| Open Homepage | `Cmd+P` → "Homepage: Open homepage" |
| Open Map | `Cmd+P` → "Map View: Open map" |
| Create/edit task | `Cmd+P` → "Tasks: Create or edit task" |
| Insert template | `Cmd+P` → "Templater: Insert Template" |
| Toggle reading mode | `Cmd+E` |
| Command palette | `Cmd+P` |

---

## Changelog

See [Resources/Patch Notes.md](Resources/Patch%20Notes.md) for full version history.

| Version | Date | Summary |
| :------ | :--- | :------ |
| v1.1 | 2026-04-25 | Added Templater, QuickAdd, Kanban, Leaflet, Tasks — pre-configured with data.json files |
| v1.0 | 2026-04-25 | Initial vault — Dataview dashboard, Map View, listing template, search sources, criteria note |
