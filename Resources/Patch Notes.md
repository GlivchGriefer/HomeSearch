---
title: Patch Notes
tags:
  - type/reference
created: 2026-04-25
---

# Patch Notes

> [!info] Purpose
> Version history for this vault — tracks structural changes, plugin additions, template updates, and workflow improvements. Add an entry here whenever the vault structure or a plugin configuration changes.

---

## v1.1 — 2026-04-25

**Plugin expansion — pre-restart configuration**

### Added Plugins
- **Templater** v2.19.3 — Auto-fills `created` date and title on note creation; folder trigger configured for `01 - Listings/`
- **QuickAdd** v2.12.0 — "New Listing" command wired to template + `01 - Listings/` destination
- **Kanban** v2.0.51 — Pipeline board with linked-page metadata (rent, beds, commute, rating); tag colors for status
- **Obsidian Leaflet** v6.0.5 — Radius buffer map with work-address anchor and auto-markers from `01 - Listings/`
- **Tasks** v7.23.1 — Due dates and recurrence on listing checklist items; scoped to `01 - Listings/`

### New Plugin Data Files
- `.obsidian/plugins/templater-obsidian/data.json` — folder template mapping, trigger-on-create enabled
- `.obsidian/plugins/quickadd/data.json` — "New Listing" template choice, address prompt as filename
- `.obsidian/plugins/obsidian-kanban/data.json` — lane settings, linked metadata fields, tag color rules
- `.obsidian/plugins/obsidian-tasks-plugin/data.json` — global scope to `01 - Listings/`, created-date tracking

### New Notes
- `00 - Pipeline.md` — Kanban board with 5 lanes: Active, Viewing Scheduled, Applied, Offer/Negotiating, Archive
- `04 - Neighborhoods/Commute Map.md` — Leaflet embed with 3 radius circles (5/10/15 mi) and `markerFolder` auto-pull
- `README.md` — Full plugin guide, YAML field reference, AI workflow, Dataview snippets
- `Resources/Patch Notes.md` — This file

### Updated Files
- `_templates/Listing Template.md` — Added Templater syntax: `tp.file.title` for title/address, `tp.date.now()` for created date, `tp.file.cursor()` for auto-cursor after Notes section; Tasks-compatible due-date syntax on timeline items
- `community-plugins.json` — Added: `templater-obsidian`, `quickadd`, `obsidian-kanban`, `obsidian-leaflet-plugin`, `obsidian-tasks-plugin`
- `Home.md` — Added links to Pipeline and Commute Map

### Pending After Restart
- [ ] Verify Templater triggers on new note creation in `01 - Listings/`
- [ ] Verify QuickAdd "New Listing" command appears in Command Palette
- [ ] Assign hotkey to QuickAdd New Listing (`Cmd+Shift+N` recommended)
- [ ] Set Kanban lane in `00 - Pipeline.md` to kanban view mode
- [x] Update `work_lat` / `work_lng` in `04 - Neighborhoods/Commute Map.md`
- [x] Update map center coords in `Home.md` mapview block and `Commute Map.md` leaflet block

---

## v1.0 — 2026-04-25

**Initial vault build**

### Plugins Enabled
- Banners, Iconize, Ink, Map View v6.1.4, Homepage v4.4.0, Dataview v0.5.68

### Files Created
- `Home.md` — Dashboard with Dataview stats, Map View embed, collapsed BASE table, search sources index
- `01 - Listings/` — Empty; receives listing notes
- `02 - Search Sources/` — Zillow, Apartments.com, Realtor.com, Craigslist, Facebook Marketplace
- `03 - Criteria/Search Criteria.md` — YAML-driven requirements, priority weighting guide, AI search prompt template
- `04 - Neighborhoods/` — Empty placeholder
- `05 - Archive/` — Empty
- `_templates/Listing Template.md` — ~30-field YAML schema, costs table, contact table, commute section, questions checklist, timeline tasks

### Plugin Config
- `homepage/data.json` — Points to `Home.md`, opens on startup, refreshes Dataview
- `community-plugins.json` — Added Dataview (was installed but not enabled)

---

## How to Add an Entry

When you make a structural change to the vault:

```markdown
## vX.Y — YYYY-MM-DD

**Short description of the change**

### What Changed
- Item 1
- Item 2

### Why
Brief reason for the change.
```

Use semantic versioning loosely:
- **Major (v2.0)** — Full restructure, new workflow, breaking template changes
- **Minor (v1.1)** — New notes, new plugins, significant additions
- **Patch (v1.0.1)** — Small fixes, typo corrections, field additions
