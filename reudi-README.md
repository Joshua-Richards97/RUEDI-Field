# Reudi Field

**MiniRUEDI Gas Analysis & Groundwater Monitoring** — a mobile-first Progressive Web App for field hydrogeologists running MiniRUEDI dissolved gas analysis campaigns.

---

## Features

### REUDI Gas Analysis
- Complete digital field sheet matching the MiniRUEDI paper form (MiniRUEDI Analysis - RWI | UniBe)
- **Site identification:** Project, date, location/BH ID, sampler, sample depth, GPS capture
- **Well parameters:** Water level, well volume, pumped volume, air/water temp, humidity, CHEM/GAS sampling checkboxes
- **MiniRUEDI timestamps:** Blanks, Standard_AIR, Standard_GASMIX — each with dual time fields and "taken earlier this day" checkbox
- **Dynamic sample analysis sequences** — start with 3, add or remove as needed; each has Std. Before, Std. After, and Blank Taken checkboxes
- **Water sampling (CHEM):** pH, Eh, EC — each with paired temperature
- **Comments/field notes**
- Save, edit, delete records
- Export individual or project-filtered records as PDF field sheet or CSV

### Groundwater Levels
- Create monitoring points with coordinates, TOC RL, diameter, depth
- Record water level readings over time with datetime, sampler, notes, photos
- Trend chart and statistics (latest, shallowest, deepest, range)
- Differential calculator between any two readings
- Export CSV or PDF per point

### Borehole Volume Calculator
- Diameter (mm/inches), well depth, water level, stand-up
- Calculates standing water volume and 3× purge volume
- Live annotated cross-section diagram
- GPS capture, site photos, field notes

### Project System
- Create projects with name, client, reference/job number, notes
- Active project shown as top banner on all screens — tap to switch or create new
- All records linked to projects — filter and export by project

### Logs & Export
- **Reudi Data** tab: filter by project, export filtered records as combined CSV or multi-page PDF field sheets
- **Calculator** and **GW Levels** tabs with same filter/export capability
- Full JSON backup/restore

### Offline-Ready PWA
- Installs to home screen (iOS/Android)
- Works fully offline after first load

---

## Files

| File | Purpose |
|------|---------|
| `reudi-field.html` | Main application — single file, zero dependencies |
| `reudi-manifest.json` | PWA manifest — name, icons, shortcuts |
| `reudi-service-worker.js` | Offline cache |
| `reudi-icon-192.png` | App icon 192×192 |
| `reudi-icon-192-maskable.png` | Android adaptive icon 192×192 |
| `reudi-icon-512.png` | App icon 512×512 |
| `reudi-icon-512-maskable.png` | Android adaptive icon 512×512 |
| `reudi-icon-1024.png` | High-res icon for App Store/Play Store |
| `reudi-icon-180.png` | Apple Touch Icon |
| `reudi-icon-96.png` | Favicon |

---

## Deployment — GitHub Pages

1. Create a new GitHub repository (e.g. `ReudiField`)
2. Upload all files from the zip
3. Go to **Settings → Pages → Source** → branch: `main`, folder: `/ (root)` → Save
4. App live at: `https://yourusername.github.io/ReudiField/reudi-field.html`

**Install on Android:** Open URL in Chrome → three-dot menu → **Add to Home Screen** / **Install App**

**Install on iPhone:** Open URL in Safari → Share → **Add to Home Screen**

---

## Updating the App

1. Download the new zip from Claude, unzip
2. In your GitHub repo: **Add file → Upload files**, drag all new files in
3. Commit with a message like `Update v2 — GPS and project export`
4. Bump `CACHE_VERSION` in `reudi-service-worker.js` (e.g. `v1` → `v2`) — this forces installed apps to fetch the new version
5. Devices update automatically on next open

---

## Data Storage

All data stored in browser `localStorage` (~5 MB). Use **Logs → Backup All Data** to export a JSON file. Restore on any device via **Restore Backup**.

---

## Field Sheet Format

The PDF export matches the **MiniRUEDI Analysis v1.2** paper form used by RWI | UniBe — same section layout, same terminology, suitable for inclusion in sampling reports.

---

## Built With

Pure HTML, CSS and JavaScript — zero dependencies, zero build step. Runs entirely in the browser.

*Reudi Field · MiniRUEDI Gas Analysis & GW Monitoring*
