# Portfolio Presentation — 7 Slides

> A 5–7 minute structured walkthrough for showcasing the full 60-day portfolio project to an audience of developers, hiring managers, or technical evaluators.

---

## Slide 1 — Title & Introduction

**Headline:** From Zero to Production — A 60-Day Full-Stack Portfolio

**Content:**
- Your name and role (e.g. Frontend Developer / Full-Stack Developer)
- The challenge: build four production-ready web projects from scratch in 60 days
- Technologies used at a glance: HTML5 · CSS3 · Vanilla JavaScript · REST APIs · PWA
- Live demo link and GitHub repository URL

**Visual:** Full-width screenshot of the portfolio landing page (`index.html`)

**Speaker notes:**
> "This portfolio demonstrates a structured progression from static HTML foundations all the way to an offline-capable Progressive Web App — each project introducing a new tier of web technology without relying on any framework."

---

## Slide 2 — Project 1: Aether Studio (Static Website)

**Headline:** Semantic HTML & Advanced CSS Mastery

**Content:**
- 6-page creative agency website — Home, About, Services, Portfolio, Blog, Contact
- CSS-only testimonial slider (radio `:checked` state, zero JS)
- CSS-only portfolio category filter with instant sibling transitions
- Responsive side-drawer hamburger navigation
- Dark-mode Google Maps via CSS `invert` + `hue-rotate`
- Lighthouse score: 95+ Performance, 98+ Accessibility

**Visual:** Side-by-side desktop and mobile screenshots of the homepage

**Key talking point:**
> "The slider and filter are entirely CSS-driven — no JavaScript at all. This demonstrates a deep understanding of the cascade and state management through HTML semantics."

---

## Slide 3 — Project 2: JavaScript Showcase Hub (13 Components)

**Headline:** Vanilla JavaScript — DOM, Events & State

**Content:**
- 13 production-grade interactive components built from scratch
- Highlights: image carousel with touch swipes, countdown modal with focus trap, drag-and-drop reorderer
- Real-time form validation + password strength meter
- Dark/light mode toggle persisted via `localStorage`
- IntersectionObserver for stat counter animations

**Visual:** Grid collage of all 13 component demos (screenshot)

**Key talking point:**
> "Every component is written without any library or framework — pure ES6+ JavaScript. This showcases event delegation, closures, and browser APIs that most developers take for granted via packages."

---

## Slide 4 — Project 3: API Studio (REST API Dashboard)

**Headline:** Async JavaScript, REST APIs & Error-Resilient UX

**Content:**
- Three mini-apps in a single SPA: Weather Station, Movie Searcher, People & Quotes Hub
- `AbortController` cancels in-flight requests on rapid input
- Graceful fallbacks: all features work with zero API keys using Open-Meteo, DummyJSON, RandomUser
- Weather: geolocation, 5-day forecast, unit toggle, recent search history
- Movies: debounced autocomplete, filters, favorites drawer, detail modal, pagination
- Profiles: vCard RFC 6350 download, saved contacts list, clipboard + tweet share

**Visual:** Screenshot of the API Studio dashboard with all four tabs visible

**Key talking point:**
> "The most common failure in API apps is a bad offline or error experience. Every data source here has a fallback, every network call has an AbortController, and every error state has an informative UI — it works out of the box without a single API key."

---

## Slide 5 — Project 4: Veloce Expense Tracker (PWA)

**Headline:** IndexedDB, Service Workers & Performance Engineering

**Content:**
- Full offline-first PWA — all CRUD works with no internet connection
- IndexedDB for large structured data (no 5 MB localStorage limit)
- Client-side WebP compression via Canvas API (receipts shrink 40–70%)
- Dynamic code-splitting: Chart.js only loads when the Analytics tab opens
- Infinite scroll batching (10 items/page) + debounced search + 4-way sort
- Budget alert system with browser push notifications at 90% and 100% thresholds
- JSON backup export/import with Base64-serialised receipt blobs

**Visual:** Split screenshot — Veloce Dashboard (left) and Analytics panel with charts (right)

**Key talking point:**
> "Veloce is a fully production-engineered app. The Service Worker pre-caches all shell assets, IndexedDB replaces localStorage for binary data, and performance techniques like debounce, throttle, and lazy loading keep it running at 98+ Lighthouse."

---

## Slide 6 — Performance, Accessibility & Testing

**Headline:** Production Quality — Not Just Working Code

**Content:**

**Lighthouse Results**
| Project | Perf | A11y | Best Practices | SEO |
|---------|------|------|----------------|-----|
| Aether Studio | 95+ | 98+ | 100 | 100 |
| JS Showcase | 97+ | 98+ | 100 | 98+ |
| API Studio | 90+ | 95+ | 100 | 95+ |
| Veloce (dist/) | 98+ | 98+ | 100 | 98+ |

**Accessibility highlights:**
- Focus trapping in all modals (Tab / Shift+Tab cycle locked inside dialog)
- `aria-live` regions for toast notifications (screen reader compatible)
- Skip-to-content link on every page
- All interactive elements have visible focus rings and ARIA labels

**Testing coverage:**
- Cross-browser: Chrome, Firefox, Safari, Edge
- Cross-device: Desktop (1440px), Laptop (1280px), Tablet (768px), Mobile (375px)
- API scenarios: offline mode, invalid input, rate-limit fallback, AbortError handling

**Visual:** Lighthouse report screenshot for Veloce showing 98+ across all four categories

---

## Slide 7 — Deployment, GitHub & What's Next

**Headline:** Live, Tagged & Production-Ready

**Content:**

**Deployment**
- Hosted on **Netlify** with auto-deploy from GitHub `main` branch
- `netlify.toml` configures: redirect rules, security headers (`X-Frame-Options`, `X-Content-Type-Options`), cache policies, Service Worker no-cache header
- Live URL: [https://YOUR-SITE-NAME.netlify.app](https://YOUR-SITE-NAME.netlify.app)

**Repository hygiene**
- All `console.log` / `debugger` statements removed from production code
- `.gitignore` excludes `node_modules/`, `.env`, `.DS_Store`, build artefacts
- `.env.example` documents every API key with step-by-step setup instructions
- Production tag: `v2.0.0`

**What I would add next:**
- TypeScript migration for type safety across the codebase
- Unit tests with Vitest for utility functions and DB layer
- CI/CD pipeline with GitHub Actions for lint + lighthouse checks on every PR
- React or Svelte rewrite of Veloce to compare DX and bundle size

**Visual:** GitHub repository view showing the production tag, commit history, and Netlify deploy badge

**Speaker closing:**
> "Everything in this portfolio — the code, the UX, the deployment config — was written by hand without a framework or starter template. The goal was to deeply understand the web platform before abstracting it. I'm now ready to bring those fundamentals into any modern stack."

---

## Presentation Tips

- **Total runtime:** 6–7 minutes at a comfortable pace (slides 1–2 are 30–45s each, slides 3–6 are 60–90s each, slide 7 is 45–60s)
- Open each live project in a separate browser tab before the presentation starts
- Show the mobile view of at least one project using Chrome DevTools device emulator live
- Keep the Lighthouse report tab open to show scores live on Slide 6
- End by navigating to the GitHub repo and clicking the Netlify badge for a live deploy confirmation
