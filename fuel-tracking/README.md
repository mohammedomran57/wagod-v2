# WAQOOD — Libya fuel station prototype

Open `index.html` in a browser. For consistent browser storage and geolocation, serve this folder locally:

```sh
python -m http.server 8765 --bind 127.0.0.1
```

Then open http://127.0.0.1:8765. No build or package installation is required. Google Fonts is optional; system fonts are the fallback. Directions open Google Maps. Location requires browser permission and localhost or HTTPS; coordinates are held in memory, not stored by this app.

## Changes

- Arabic RTL and English LTR responsive citizen interface.
- Separate opening status, fuel availability and estimated queue time.
- Search in either language, fuel and open-only filters, favorites, shortest-wait and freshness sorting, optional straight-line distance sorting.
- Timestamp aging and explicit stale-data notices after 30 minutes.
- Local complaint records with unique reference numbers, validation and escaped display text. Reports remain unverified and do not overwrite station records.
- Derived operational metrics, attention list, CSV download, browser print-to-PDF and explicitly illustrative supply simulation.
- No mandatory JavaScript CDN dependencies.

`original.html` preserves the supplied prototype, including its embedded map and original charts. This alternate citizen-focused version uses per-station directions links instead of an embedded map, and a transparent supply scenario instead of the original hardcoded 30-day forecast. Seed names and coordinates are copied from the supplied prototype and are not independently verified.

## Demo boundaries

This is a front-end prototype, not a deployed ministry service. Station data is illustrative. Favorites and reports live in this browser's localStorage under `waqood-demo-v1`; no report is transmitted. There is no authentication, multi-user synchronization, authorized station update workflow or actual dispatch. A clearly marked TEST ONLY report may appear in the local preview from verification; it is not bundled in the source files.

For a production pilot, add authenticated operator and ministry roles, a station registry with verified coordinates and hours, timestamped fuel/queue updates, server-side report validation and moderation, an audit trail, and an authenticated API/database. Establish a real update source and queue estimation method before presenting live availability or forecasts.

## Verification

- Node syntax checks passed for app.js and stations.js.
- Browser-verified Arabic initial rendering, search for Janzour, English switching, report dialog selection, local submission and persistence after reload.
- Arabic mobile layout checked at 390 × 844; document had no horizontal overflow.
- Preview screenshot saved as preview.png.
- Location permission/success, external directions, CSV download and print output were not exercised end-to-end.

Files: index.html (markup), style.css (responsive styles), app.js (behavior), stations.js (sample data).
