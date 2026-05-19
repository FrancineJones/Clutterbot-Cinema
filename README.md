# Habitat — Cinema Atlas

An interactive UX/UI prototype for Clutterbot's internal environmental modelling tool.

The first build — **Cinema Atlas** — turns five field-visit reports into a single, navigable model of cinema environments that researchers, designers, and engineers can all read from.

## What's in this repo

- `index.html` — single-file prototype (no build step, no dependencies)

That's it. Open it in any modern browser and it runs.

## What you'll see

- **Overview** — KPI strip, between-screening turnaround chart, the five environments, items observed, and patterns we keep noticing
- **Environments** — switchable Grid / Table / Map views (the map shows a stylised outline of New Zealand with pins for each cinema)
- **Site details** — full measurement grids, photos from the visit, edge cases, and observation notes per site
- **Seat types** — every seat archetype catalogued across the five sites
- **Object library** — items observed in cinemas, with photo galleries
- **Photo library** — every field photo with cinema + subject filters
- **Behaviour notes** — peak mess line graph, cleaning workflows, and cleanliness expectations
- **Edge cases** — 18 catalogued unusual findings, filterable and severity-editable
- **Compare** — side-by-side metrics across multiple sites
- **Data model** — the underlying JSON shape
- **Embedded onboarding** — spotlight coachmarks that walk first-time users through the interface
- **Global search** — `⌘K` searches sites, objects, edge cases, and measurements with a no-results state

## Running it

```bash
open index.html              # macOS
xdg-open index.html          # Linux
start index.html             # Windows
```

Or serve locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying with GitHub Pages

Because the prototype is a single static `index.html`, GitHub Pages works out of the box:

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. After ~30 seconds your prototype will be live at `https://<your-username>.github.io/<repo-name>/`.

## A note on photos

The prototype references a `photos/` folder for site cover images, the object library, the photo library, and the per-site galleries. That folder is **not included in this repo** — it contains real research photos and lives separately.

Without `photos/` next to `index.html`, you'll see:
- Site cards using their stylised archetype placeholders (this is the intended fallback)
- Photo library empty state
- Object tiles using icon placeholders
- Site detail photo grid showing the "no photos yet" state

Drop a `photos/` folder next to `index.html` and the prototype lights up.

## Source data

Built from real field reports covering:

| Site | Type | Visits |
|------|------|--------|
| Event Cinema — Queensgate | Multiplex | 2 |
| Embassy Theatre — Wellington | Heritage premium | 1 |
| Roxy Theatre — Miramar | Boutique | 1 |
| Luxe Cinema — Papamoa | Boutique luxury | 1 |
| United Cinemas — Mount Maunganui | Mainstream chain | 1 |

All measurements, edge cases, and observations come directly from those reports — no values were fabricated.

## Tech

- Pure HTML, CSS, and vanilla JavaScript
- No frameworks, no build step
- Inline SVG for icons, charts, the map, and the Clutterbot logo
- Designed for `1400px+` desktop layouts (responsive down to ~1200px)

## License

Internal — Clutterbot.
