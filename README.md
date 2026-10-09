# Less JavaScript, More Platform

**Modern Browser APIs Front-End Developers Should Actually Use**  
Courtney Yatteau · TechBash 2026

Modern browsers can handle many interface behaviors that front-end developers still reach for JavaScript to build themselves. This talk looks at practical ways to let the platform own more of the generic UI plumbing while keeping JavaScript focused on application-specific behavior.

## PAUSE before reaching for JavaScript

- **P** — Pause before reaching for JavaScript
- **A** — Ask what HTML and CSS can already do
- **U** — Use the browser platform
- **S** — Study support and progressive enhancement
- **E** — Employ JavaScript where it adds real value

The recurring question throughout the talk is:

> **Do I actually need JavaScript for this?**

## What the talk covers

- Native `<dialog>`
- Invoker Commands with `command` and `commandfor`
- Popover API
- Native form validation
- View Transitions
- Progressive enhancement and browser-support decisions
- When JavaScript is still the right tool

The City Explorer demos use an ArcGIS map as an example of JavaScript doing specialized work that should stay, while the surrounding UI gets simpler.

## Demo files

Each demo is a standalone HTML file with its CSS and JavaScript inlined. There is no npm install or build step.

### City Explorer

1. [`00-start.html`](demos/city-explorer/00-start.html) — custom JavaScript modal
2. [`01-dialog.html`](demos/city-explorer/01-dialog.html) — native `<dialog>`
3. [`02-commands.html`](demos/city-explorer/02-commands.html) — Invoker Commands
4. [`03-popover.html`](demos/city-explorer/03-popover.html) — Popover API + category filtering
5. [`04-transitions.html`](demos/city-explorer/04-transitions.html) — abrupt selected-place state change
6. [`05-complete.html`](demos/city-explorer/05-complete.html) — same state change with View Transitions

### Forms

- [`00-custom.html`](demos/forms/00-custom.html) — custom JavaScript validation
- [`01-native.html`](demos/forms/01-native.html) — native HTML validation

## Running the demos

The form demos can be opened directly in a browser.

The City Explorer demos use the ArcGIS Maps SDK for JavaScript and require an ArcGIS API key for the basemap. The public files intentionally contain this placeholder:

```text
YOUR_FRESH_RESTRICTED_ARCGIS_API_KEY
```

Replace that value in your local copy with your own appropriately restricted API key before running the map demos.

For the smoothest local setup, serve the repo with a tiny local web server instead of opening the files with `file://`:

```bash
python -m http.server 8080
```

Then open the demo you want from `http://localhost:8080/`.

## Slides and speaker notes

- [TechBash 2026 slides](slides/Less-JavaScript-More-Platform-TechBash-2026.pptx)
- [Demo speaker script](speaker-notes/Demo-Speaker-Script.docx)

The PowerPoint contains click-aligned speaker notes for the slide animations. The separate demo script covers the browser/code portions of the session.

## Key takeaway

> **Platform first. JavaScript on purpose.**

Use JavaScript for what it adds, not for what the browser already gives you.

## Speaker

Courtney Yatteau  
Developer Advocate, Esri  
GitHub: [@cyatteau](https://github.com/cyatteau)
