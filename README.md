# Less JavaScript, More Platform

**Modern Browser APIs Front-End Developers Should Actually Use**  
Courtney Yatteau | TechBash 2026

These are the demos and audience slides from the talk. The theme is to let the browser own generic interface behavior while using JavaScript intentionally for application-specific work. Even when a framework, component library, or AI assistant generates the code, it's worth asking which behaviors the app really needs to maintain.

**[View the slides (PDF, without speaker notes)](Slides.pdf)**

## Before another event listener, PAUSE

- **P** | Pause before reaching for JavaScript
- **A** | Ask what HTML and CSS can already do
- **U** | Use the browser platform
- **S** | Study support and fallbacks
- **E** | Employ JavaScript where it adds value

> Do I actually need JavaScript for this?

## Try the demos

Each is a standalone HTML file with inline CSS and JavaScript. No npm install or build step.

### City Explorer: Washington, DC landmarks

These six versions show the same mapping app as browser-native interactions replace custom UI plumbing. JavaScript still handles the ArcGIS map, place data, and filtering.

| Demo | What it illustrates |
| --- | --- |
| [00: Custom modal](demos/city-explorer/00-start.html) | A hand-rolled modal and its event listeners |
| [01: Dialog](demos/city-explorer/01-dialog.html) | The native `<dialog>` element |
| [02: Invoker Commands](demos/city-explorer/02-commands.html) | Declarative `command` and `commandfor` |
| [03: Popover](demos/city-explorer/03-popover.html) | A browser-managed filter panel, with JS still filtering data |
| [04: Abrupt transition](demos/city-explorer/04-transitions.html) | Working application-state changes without animation |
| [05: View Transitions](demos/city-explorer/05-complete.html) | The same state update enhanced with native View Transitions |

### Forms

- [Before: custom JavaScript validation](demos/forms/00-custom.html)
- [After: native HTML form constraints](demos/forms/01-native.html)

### The finale: PAUSE all together

[Open the one-page PAUSE demo](demos/PAUSE-All-Together.html) to see dialog + commands, Popover, form validation, and View Transitions in one place. This version does not require an ArcGIS API key.

## Run locally

For the forms and the PAUSE finale, you can open the HTML files directly in a modern browser. To run everything with a local server, start a server in the repository's root folder:

```bash
python -m http.server 8080
```

Then browse to `http://localhost:8080/` and open a demo file (for example, `demos/PAUSE-All-Together.html`).

### ArcGIS API key for the mapping demos

The six City Explorer files use the ArcGIS Maps SDK for JavaScript from the CDN and the `arcgis/community` basemap. They intentionally use the placeholder:

```text
YOUR_FRESH_RESTRICTED_ARCGIS_API_KEY
```

**Before running a City Explorer demo**, replace the placeholder in that HTML file with your own ArcGIS API key with access to Basemap Styles. If you plan to deploy a live demo publicly, use an appropriately restricted key (for example, authorized referrers for the domain where it is hosted). Don't commit an unrestricted development key. The local map demos depend on network access to the ArcGIS CDN and services.

The non-map demos run without any key. Use an up-to-date browser with support for the newer APIs; behavior may differ across browsers. Always verify keyboard interactions, accessibility, browser support, and reduced-motion preferences.

## Takeaway

**Platform first. JavaScript on purpose.**

The goal isn't a JavaScript-free app. It's to stop rebuilding what the browser already knows how to do.

Courtney Yatteau | Developer Advocate, Esri | [GitHub @cyatteau](https://github.com/cyatteau)
