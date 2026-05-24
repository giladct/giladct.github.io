# giladct.github.io — Portfolio Page

**Owner:** Gilad Cohen-Tal  
**Live URL:** https://giladct.github.io/  
**GitHub repo:** https://github.com/giladct/giladct.github.io  
**Local path:** `d:\gilead\ClaudeProjects\portfolio\`

---

## What This Is

A personal portfolio page showcasing Gilad's data visualization projects.  
Single-page, no framework, no build step — everything is in `index.html`.

---

## File Structure

```
portfolio/
├── index.html     # The entire page — HTML + CSS inline, no JS
├── flights.png    # Screenshot of Flight Delays Dashboard (148 KB)
├── ccarcs.png     # Screenshot of custom CCARCS web app (179 KB)
├── tableau.png    # Screenshot of Tableau CCARCS viz (1.6 MB — large, consider compressing)
└── README.md      # This file
```

---

## Page Layout

```
Header
  "My Vizzes"  ·  subtitle
  [in  Gilad Cohen-Tal]  ← LinkedIn link: https://www.linkedin.com/in/giladct/

Grid  (2-col desktop, 1-col mobile ≤720px)
  Row 1 ── Flight Delays Dashboard          [spans full width, horizontal layout]
  Row 2 ── CCARCS Custom App  |  CCARCS Tableau

Footer
  "built by giladct"  ← links to https://github.com/giladct
  + invisible Statcounter snippet (project 13250752, security key d420cfd3)
```

---

## Cards

### Row 1 — Flight Delays Dashboard  `.card-wide`
- **Screenshot:** `flights.png` (retake with Chrome headless if stale)
- **Link:** https://giladct.github.io/flights-delays/
- **Button:** "→ Live View"
- **Description:** Multi-airport delay analysis (TLV, JFK, DXB, YYZ). Data collected every 2 hours via AeroDataBox API; dashboard refreshes daily.
- **Layout note:** `.card-wide` spans `grid-column: 1 / -1`; image is 58% width, content on the right. On mobile it collapses to stacked.

### Row 2 — Canadian Civil Aircraft Register (custom)
- **Screenshot:** `ccarcs.png`
- **Link:** https://giladct.github.io/ccarcs/ (source in `d:\gilead\ClaudeProjects\index.html`)
- **Button:** "→ Live View"
- **Badge:** amber pill "Custom-built alternative" (top-right of screenshot)
- **Description:** 37,000+ aircraft, Leaflet map, no login, data updates daily.

### Row 2 — CA Aircraft Register — Tableau
- **Screenshot:** `tableau.png` (fetched from Tableau static image API: `https://public.tableau.com/static/images/CA/CARegister/CanadianCivilAircraftRegister/1.png`)
- **Link:** https://public.tableau.com/app/profile/gilad8764/viz/CARegister/CanadianCivilAircraftRegister
- **Button:** "→ View on Tableau ↗"
- **Description:** The original Tableau dashboard that inspired the custom-built version.

---

## Design System

| Token | Value | Used for |
|---|---|---|
| Navy | `#1a3a5c` | Header bg, headings, primary button |
| Navy hover | `#234d7a` | Button hover |
| Background | `#f5f6fa` | Page bg |
| White | `#fff` | Cards |
| Border | `#dde1e7` | Card borders |
| Accent | `#3b7dd8` | Focus / interactive blue |
| Font | `-apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif` | Everything |

Card previews: `height: 290px`, `object-fit: cover`, `object-position: top left`, zoom on hover (`scale(1.03)`).

---

## Deployment

- Hosted on **GitHub Pages**, branch `master`, root `/`
- Every `git push` to `master` auto-deploys (usually live within ~1 min)
- No CI, no build step — just push and it's live

### How to retake a screenshot
```powershell
# Flights
& "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" `
  --headless=new "--screenshot=C:\Users\gilead\screenshots\flights.png" `
  --window-size=1280,800 --hide-scrollbars `
  "https://giladct.github.io/flights-delays/"
Start-Sleep 5

# CCARCS custom
& "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" `
  --headless=new "--screenshot=C:\Users\gilead\screenshots\ccarcs.png" `
  --window-size=1280,800 --hide-scrollbars `
  "https://giladct.github.io/ccarcs/"
Start-Sleep 5

# Tableau (static API — no headless needed)
Invoke-WebRequest `
  -Uri "https://public.tableau.com/static/images/CA/CARegister/CanadianCivilAircraftRegister/1.png" `
  -OutFile "C:\Users\gilead\screenshots\tableau.png"

# Then copy to portfolio and push
cp C:\Users\gilead\screenshots\*.png d:\gilead\ClaudeProjects\portfolio\
cd d:\gilead\ClaudeProjects\portfolio
git add *.png && git commit -m "Refresh screenshots" && git push
```

---

## Pending Tasks

- [ ] **Compress `tableau.png`** — currently 1.6 MB, slows initial page load
- [ ] **Add OG / social meta tags** — `og:title`, `og:image`, `og:description` so the URL previews nicely when shared
- [ ] **Add favicon** — none currently; a simple navy square with "GC" initials would work
- [ ] **Add more project cards** — candidates already built in `d:\gilead\ClaudeProjects\`:
  - Ayalon Traffic Monitor (`ayalon_dashboard/`) — real-time Ayalon Highway speed tracking
  - Israel Jobs Dashboard (`il_jobs_dashboard/`) — Israeli tech job listings tracker
- [ ] **Auto-refresh screenshots** — could be done via a GitHub Actions workflow on a schedule
- [ ] **Mobile preview height** — the wide flights card collapses to 290px height on mobile; may want to tune
