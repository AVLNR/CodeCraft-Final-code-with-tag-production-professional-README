# Full-Stack Portfolio Project

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)

A complete, production-ready portfolio of four interconnected web projects built over a structured 60-day development plan. Each project targets a distinct skill area — from semantic HTML/CSS foundations to async JavaScript, REST API integration, offline-first PWA architecture, and professional deployment.


---

## Projects Overview

|---|---------|----------|-----------|

| 1 | Aether Studio — Creative Agency Website | HTML5, CSS3, Vanilla JS | [View](https://avlnr.github.io/Aether-Studio/) |

| 2 | JavaScript Showcase Hub — 12 UI Components | ES6+, CSS Variables, LocalStorage | [View](https://avlnr.github.io/Website-with-10-interactive-JS-components/) |

| 3 | API Studio — Interactive REST API Dashboard | Async/Await, Fetch, AbortController | [View]() |

| 4 | Veloce — Advanced Expense Tracker PWA | IndexedDB, Service Workers, Chart.js | [View](https://avlnr.github.io/CRUD-app-Expense-Tracker-Notes-Recipe-advanced-features/) |

---

## Features

### Task 1 — Aether Studio (6-Page Static Website)
- Premium dark-mode agency design with glassmorphic cards and neon accents
- CSS-only testimonial slider using radio button state (zero JS dependency)
- CSS-only portfolio category filter with instant transitions
- Responsive side-drawer hamburger navigation for mobile
- Dark-mode Google Maps embed via CSS `invert` + `hue-rotate`
- Interactive 3D hover team cards with reveal overlays

### Task 2 — JavaScript Showcase Hub (13 Components)
- Scroll progress bar, animated stats counters (IntersectionObserver)
- Image carousel with auto-rotate, touch swipe, and hover-pause
- Modal popups with countdown timer, backdrop close, and focus trap
- Real-time form validation with password strength meter
- Dark/Light mode toggle persisted to `localStorage`
- Drag-and-drop task reorderer with coordinate tracking

### Task 3 — API Studio (Multi-App Dashboard)
- **Weather Station**: city search + geolocation, 5-day forecast, °C/°F toggle, recent history cache
- **Movie Searcher**: debounced autocomplete, type/year filters, favorites drawer, detail modals, pagination
- **People & Quotes Hub**: quote generator with category filter, clipboard copy, tweet share; random profile generator with vCard download and contacts list
- **AbortController** request cancellation prevents race conditions
- Graceful fallbacks — all features work with zero API keys using keyless Open-Meteo, DummyJSON, and RandomUser APIs
- API status health panel with live connectivity ping

### Task 4 — Veloce Expense Tracker (PWA)
- Full **CRUD** with IndexedDB — create, read, update, delete transactions
- Receipt image upload with client-side **WebP compression** via Canvas API
- **Infinite scroll** with virtual DOM batching (10 items/page)
- **Debounced search** (300ms), category + date filters, 4-way sort
- **Chart.js analytics** — category pie chart + 6-month trend bar chart (dynamically imported)
- **Service Worker** — full offline support with pre-cached shell assets
- JSON backup export/import with Base64-serialized receipt blobs
- Budget alert banner + system push notifications at 90% and 100% thresholds
- Light/dark theme persisted to IndexedDB

---

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| Markup | HTML5 (semantic, ARIA-compliant) |
| Styling | CSS3 — Custom Properties, Flexbox, Grid, Keyframe Animations, Glassmorphism |
| Scripting | Vanilla JavaScript ES6+ — Classes, Modules, Async/Await, Promises, Destructuring |
| Data | IndexedDB (Task 4), LocalStorage (Tasks 2 & 3), JSON export/import |
| APIs | OpenWeatherMap, Open-Meteo, OMDB, RandomUser, DummyJSON Quotes |
| Charts | Chart.js (dynamically imported via code-splitting) |
| PWA | Service Workers, Web App Manifest, Offline caching |
| Performance | IntersectionObserver, debounce, throttle, Canvas WebP compression, lazy loading |
| Accessibility | Focus trapping, ARIA roles/labels, skip links, keyboard navigation, live regions |
| Deployment | Netlify (auto-deploy from GitHub) |
| Build | Custom PowerShell minifier (`build.ps1`) — 20–46% file size reduction |

---

## Screenshots

### Desktop

> **Portfolio Landing Page**
> ![Desktop Landing](./screenshots/desktop-landing.png)

> **API Studio — Weather App**
> ![Desktop Weather](./screenshots/desktop-weather.png)

> **Veloce — Analytics Dashboard**
> ![Desktop Analytics](./screenshots/desktop-analytics.png)

### Mobile

> **Portfolio Landing (375px)**
> ![Mobile Landing](./screenshots/mobile-landing.png)

> **API Studio — Movie Searcher (375px)**
> ![Mobile Movies](./screenshots/mobile-movies.png)

> **Veloce — Dashboard (375px)**
> ![Mobile Veloce](./screenshots/mobile-veloce.png)

---

## Setup Instructions

### Prerequisites
- Any modern browser (Chrome 90+, Firefox 88+, Safari 14+, Edge 90+)
- No build tools or Node.js required to run the projects
- Windows PowerShell only needed for the optional production build of Task 4

### Run Locally

**Option A — Open directly in browser (Tasks 1, 2, 3)**

Tasks 1 and 2 work by simply opening `index.html` directly in your browser:
```
File > Open File > Task 1/index.html
File > Open File > Task II/index.html
```

**Option B — Local dev server (Task 3 & Task 4)**

Tasks 3 and 4 use ES Modules and Service Workers, so they require a local server.

Using the built-in PowerShell server (Task 4):
```powershell
cd "Task 4"
powershell -ExecutionPolicy Bypass -File .\serve.ps1
# Open http://localhost:8000
```

Using VS Code Live Server (Tasks 3 & 4):
1. Install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
2. Right-click `index.html` → "Open with Live Server"

Using Python (any task):
```bash
python -m http.server 8000
# Open http://localhost:8000
```

### Build Task 4 for Production
```powershell
cd "Task 4"
powershell -ExecutionPolicy Bypass -File .\build.ps1
# Optimised output written to ./dist/
```

---

## API Keys

All projects include built-in fallbacks and work immediately without any API keys. Optional keys unlock full live data.

| Key | Used In | Fallback |
|-----|---------|----------|
| `OPENWEATHERMAP_API_KEY` | Task 3 — Weather Station | Open-Meteo (keyless) |
| `OMDB_API_KEY` | Task 3 — Movie Searcher | Built-in local movie catalog |

### How to configure

1. Copy `.env.example` to `.env`
2. Fill in your keys (see `.env.example` for step-by-step instructions to obtain each one)
3. In Task 3, open the app → click the key icon → paste keys into the Settings panel → click "Save Key Settings"

Keys are stored exclusively in your browser's `localStorage` and are never transmitted to any server.

---

## Folder Structure

```
portfolio/
│
├── Task 5/                        # Deployment root (this repo)
│   ├── index.html                 # Master landing page linking all projects
│   ├── README.md                  # This file
│   ├── .gitignore                 # Excludes secrets, deps, OS files
│   ├── .env.example               # API key template with setup instructions
│   └── netlify.toml               # Netlify deployment & redirect config
│
├── Task 1/                        # Aether Studio — 6-page agency website
│   ├── index.html                 # Homepage
│   ├── about.html
│   ├── services.html
│   ├── portfolio.html
│   ├── blog.html
│   ├── contact.html
│   ├── css/style.css
│   └── js/main.js
│
├── Task II/                       # JavaScript Showcase Hub — 13 components
│   ├── index.html
│   ├── index.css
│   └── app.js
│
├── Task III/                      # API Studio — multi-app REST dashboard
│   ├── index.html
│   ├── style.css
│   ├── app.js                     # Main SPA controller
│   └── js/
│       ├── api.js                 # HTTP client, AbortController, API integrations
│       ├── weather.js             # Weather module
│       ├── movies.js              # Movies module
│       └── profiles.js            # Profiles & quotes module
│
└── Task 4/                        # Veloce — PWA expense tracker
    ├── index.html
    ├── styles.css
    ├── app.js                     # Main controller (CRUD, filters, modals)
    ├── db.js                      # IndexedDB manager
    ├── utils.js                   # Debounce, throttle, WebP compression, focus trap
    ├── charts.js                  # Chart.js dynamic module (code-split)
    ├── sw.js                      # Service Worker (offline cache)
    ├── sw-register.js             # Service Worker registration
    ├── build.ps1                  # Production minifier script
    ├── serve.ps1                  # Local dev server
    └── dist/                      # Compiled production build output
```

---

## Deployment

This project is deployed via **Netlify** with automatic deploys on every push to `main`.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/YOUR-USERNAME/YOUR-REPO)

### Manual Deploy Steps
1. Fork or clone this repository
2. Log in to [Netlify](https://app.netlify.com)
3. Click **Add new site** → **Import an existing project**
4. Connect your GitHub account and select this repository
5. Set publish directory to `.` (root)
6. Click **Deploy site**
7. Optionally configure a custom subdomain under **Domain settings**

The `netlify.toml` in this repo handles all routing and caching headers automatically.

---

## Lighthouse Scores (Target)

| Project | Performance | Accessibility | Best Practices | SEO |
|---------|-------------|---------------|----------------|-----|
| Task 1 — Aether Studio | 95+ | 98+ | 100 | 100 |
| Task 2 — JS Showcase | 97+ | 98+ | 100 | 98+ |
| Task 3 — API Studio | 90+ | 95+ | 100 | 95+ |
| Task 4 — Veloce (dist/) | 98+ | 98+ | 100 | 98+ |

---

## Browser & Device Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 90+ | Fully supported |
| Firefox | 88+ | Fully supported |
| Safari | 14+ | Fully supported |
| Edge | 90+ | Fully supported |

Tested on Desktop, Laptop, Tablet (768px), and Mobile (375px) viewport breakpoints.

---

## License

This project is open-source under the [MIT License](LICENSE).

---




