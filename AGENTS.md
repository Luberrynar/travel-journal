# AGENTS.md — My Travel Journal (ခရီးသွားမှတ်တမ်း)

Read this file fully before creating or editing anything in this repository.

## 1. Purpose
A personal travel journal website. Each trip is ONE page. The site is meant to grow over time: the owner will keep adding new trips, so every page must follow the same structure and style.
- Audience: the owner, plus friends and classmates who read the pages in a browser.
- Primary job: make each trip easy to read and easy to add.

## 2. Tech stack (do not change)
- Plain HTML + CSS only. No framework, no build step, no npm.
- Hosted on GitHub Pages from the `main` branch, root folder.
- JavaScript is not needed. Do not add it unless the owner asks.
- All links are RELATIVE (e.g. `pages/bagan.html`, `../assets/css/style.css`) so the site works under `https://<user>.github.io/<repo>/`.

## 3. Folder structure
```
/
├── AGENTS.md              this file
├── index.html             home page: list of all trips, newest first
├── assets/
│   ├── css/style.css      the ONLY stylesheet (all design tokens live here)
│   └── img/               photos, named <trip-slug>-<nn>.jpg
└── pages/
    ├── _template.html     copy this to start a new trip
    └── <trip-slug>.html   one file per trip
```
Never put CSS inside page files. Never create other folders without asking.

## 4. Naming rules
- Trip file: `pages/<place>.html`, lowercase English, words joined by `-` (e.g. `bagan.html`, `chiang-mai-2026.html`). Add the year only if the same place is visited twice.
- Images: `assets/img/<trip-slug>-01.jpg`, `-02.jpg`, … JPG, under 300 KB each.
- Every `<img>` has a meaningful `alt` text and sits inside `<figure>` with a `<figcaption>`.

## 5. Design rules
Edit colors and fonts ONLY through the CSS variables at the top of `style.css`.
- Colors: background `#F2F6F7`, ink `#1B2A32`, accent (sea blue) `#0F6E8C`, highlight (marigold) `#E8A33D`, line `#C9D6DB`.
- Fonts: headings Newsreader (serif), body Noto Sans Myanmar (falls back to system sans). Line length under 70 characters (`max-width: 40rem` for text).
- Layout: left-aligned, single column, generous spacing. No card grids, no shadows, no gradients.
- The signature element is the route line: a vertical line with dots on the home page (trips) and on the “Route” section of each trip page. Use it only for real sequences.
- Must stay readable on a phone (test at 375 px width).

## 6. Page format for a trip (`pages/<trip-slug>.html`)
Keep this order. Do not skip or reorder sections.
1. `<header>`: link back to `../index.html`, then `<h1>` with the place name in Burmese and English (e.g. `ပုဂံ · Bagan`).
2. `<dl class="meta">`: Date, Place, Travelled with, Budget (optional rows may say `-`).
3. Summary: one short paragraph, 2–3 sentences.
4. `<h2>Route</h2>`: `<ol class="route">`, one `<li>` per stop, in visit order.
5. `<h2>Highlights</h2>`: 3–5 short paragraphs or a list, with photos in `<figure>`.
6. `<h2>Tips</h2>`: practical advice for a future visitor (cost, transport, season).
7. `<footer>`: link back to the home page.

## 7. Language rules
- Page content: Burmese is the main language. Place names and section headings are bilingual or English as shown above.
- Do not translate or rewrite the owner's own words. Fix only spelling mistakes, and say what you fixed.
- Never invent facts, prices, or opening hours. If something is missing, write `TODO: <what is missing>` as an HTML comment and tell the owner.

## 8. How to add a new trip (step by step)
1. Copy `pages/_template.html` to `pages/<trip-slug>.html`.
2. Replace every placeholder in the new file. Update `<title>` and the `<h1>`.
3. Put photos in `assets/img/` using the naming rule.
4. In `index.html`, add a new `<li>` at the TOP of the trip list, copying the existing item format (date, title, one-line summary, link).
5. Run the checklist in section 10.

## 9. Rules for AI
DO:
- Follow sections 3–8 exactly, even for small edits.
- Reuse existing CSS classes. If a new class is truly needed, add it to `style.css` and explain why.
- Reply with a short list of files created or changed.

DO NOT:
- Delete or rewrite existing trip pages unless asked.
- Add external libraries, trackers, ads, or remote images.
- Change this `AGENTS.md` unless the owner asks. If a rule seems wrong, say so and ask.

## 10. Checklist before finishing
- [ ] New page opens by double-clicking the file, with the style applied.
- [ ] All links work (home ↔ trip) and are relative.
- [ ] Sections follow the order in section 6.
- [ ] `index.html` lists the new trip at the top.
- [ ] File and image names follow section 4.
- [ ] Looks fine at 375 px width.

## 11. Example prompt
> Read AGENTS.md. Add a new trip page for Inle Lake (date: 3–5 Dec 2026). Here are my notes: …
