# giladct.github.io — Portfolio Page

**Live URL:** https://giladct.github.io/

Personal portfolio page for Gilad Cohen-Tal showcasing data visualization projects.

---

## Architecture

### Files
| File | Size | Purpose |
|---|---|---|
| `index.html` | 9 KB | Single self-contained page — all HTML, CSS, and JS inline |
| `flights.png` | 148 KB | Screenshot of the Flight Delays Dashboard |
| `ccarcs.png` | 179 KB | Screenshot of the custom CCARCS web app |
| `tableau.png` | 1.6 MB | Screenshot of the original Tableau CCARCS viz (fetched from Tableau's static image API) |

### Layout
```
Header
  └─ "My Vizzes" title + subtitle
  └─ LinkedIn pill link (Gilad Cohen-Tal)

Grid (2-column CSS Grid, collapses to 1 on mobile ≤720px)
  ├─ Row 1: Flight Delays Dashboard   [spans full width, horizontal layout]
  └─ Row 2: CCARCS Custom App  |  CCARCS Tableau Version

Footer
  └─ "built by giladct" link
  └─ Statcounter analytics snippet
```

### Tech
- Vanilla HTML/CSS — no frameworks, no build step
- All CSS inlined in `<style>` block
- Screenshots are static PNG files (no external image services)
- Hosted on GitHub Pages, deployed from `master` branch root
- Analytics via Statcounter (project 13250752)

### Design tokens
| Token | Value |
|---|---|
| Navy (primary) | `#1a3a5c` |
| Background | `#f5f6fa` |
| Border | `#dde1e7` |
| Accent blue | `#3b7dd8` |
| Font | system sans-serif (`-apple-system`, `Segoe UI`, …) |

---

## Featured Projects

### 1. Flight Delays Dashboard
- **URL:** https://giladct.github.io/flights-delays/
- **Source repo:** `giladct/flights-delays`
- Tracks departure delays at TLV, JFK, DXB, YYZ
- Data collected every 2 hours via AeroDataBox API; dashboard refreshes daily

### 2. Canadian Civil Aircraft Register (custom)
- **URL:** https://giladct.github.io/ccarcs/
- **Source repo:** `giladct/ClaudeProjects` (root `index.html`)
- Searchable registry of 37,000+ aircraft with Leaflet map; no login required
- Data updates daily

### 3. Canadian Civil Aircraft Register (Tableau)
- **URL:** https://public.tableau.com/app/profile/gilad8764/viz/CARegister/CanadianCivilAircraftRegister
- Original Tableau Public dashboard that inspired the custom-built version

---

## Pending / Nice-to-Have

- [ ] **tableau.png is 1.6 MB** — compress or resize before next deploy to improve load time
- [ ] **Screenshots go stale** — no automated re-screenshot process; retake manually when dashboards change significantly
- [ ] **Add more projects** — Ayalon Traffic Monitor and Israel Jobs Dashboard are candidates for a third row
- [ ] **OG / social meta tags** — add `<meta property="og:image">` etc. for better link previews when sharing the URL
- [ ] **Favicon** — currently none; a simple navy square with initials would complete the look
- [ ] **Mobile screenshot preview height** — wide flights card collapses to 290px on mobile, which may cut off important parts of the screenshot
