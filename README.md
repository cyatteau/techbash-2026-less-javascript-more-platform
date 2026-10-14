# Less JavaScript, More Platform

**Modern Browser APIs Front-End Developers Should Actually Use**  
Courtney Yatteau | TechBash 2026

These are the demos and audience slides from the talk. The theme is to let the browser own generic interface behavior while using JavaScript intentionally for application-specific work. Even when a framework, component library, or AI assistant generates the code, it's worth asking which behaviors the app really needs to maintain.

**[View the slides](Slides.pdf)**

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

**Before running a City Explorer demo**, create a key with access to the Basemap styles service and replace the placeholder in that file. See the step-by-step instructions below. The mapping demos need network access to the ArcGIS CDN and services.

The non-map demos run without any key. Use an up-to-date browser with support for the newer APIs; behavior may differ across browsers. Always verify keyboard interactions, accessibility, browser support, and reduced-motion preferences.

### Get your own API key (ArcGIS Location Platform)

1. Sign in at **[location.arcgis.com](https://location.arcgis.com/)** with an ArcGIS Location Platform account. Select **My portal**.
2. In your portal, go to **Content > My content > New item > Developer credentials > API key credentials**.
3. Choose **Public application**, and enable the **Basemap styles service** privilege (`premium:user:basemaps`) for these demos. You do not need Places, Routing, or other privileges for the sample basemap.
4. Follow the credential setup steps, configure appropriate **referrer restrictions** for your local or hosted site, generate an API key, and copy it. If using localhost and a hosted GitHub Pages site, account for both environments in your settings.
5. Replace `YOUR_FRESH_RESTRICTED_ARCGIS_API_KEY` in each City Explorer HTML file you want to run. **Do not commit an unrestricted key to a public repository.** Keep your test key local, and use appropriately scoped credentials if publishing a live app.

For illustrated, up-to-date setup instructions, see Esri's **[Create an API key tutorial](https://developers.arcgis.com/documentation/security-and-authentication/api-key-authentication/tutorials/create-an-api-key/location-platform/)**. Creating credentials requires an account with sufficient privileges.

## Resources and documentation

### Modern browser APIs used in this talk

| Feature | Documentation |
| --- | --- |
| Native modal dialogs | [MDN: `<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/dialog) and [`showModal()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement/showModal) |
| Invoker Commands | [MDN: Invoker Commands API](https://developer.mozilla.org/en-US/docs/Web/API/Invoker_Commands_API) (`command`, `commandfor`) |
| Popover API | [MDN: Popover API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API) (`popover`, `popovertarget`) |
| Native form validation | [MDN: Client-side form validation](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/Form_validation) (`required`, `type`, `min`, `max`) |
| View Transitions | [MDN: View Transition API](https://developer.mozilla.org/en-US/docs/Web/API/View_Transition_API) and [`document.startViewTransition()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/startViewTransition) |

MDN reference pages include **browser compatibility** tables. Check support and test keyboard interaction, accessibility, and reduced-motion behavior in your target browsers. Remember that browser form validation improves the experience, but **server-side validation is still required** for real submissions.

### ArcGIS mapping resources

- **[ArcGIS Maps SDK for JavaScript documentation](https://developers.arcgis.com/javascript/latest/)**: API reference, examples, and guides for the mapping portion of City Explorer.
- **[Get started with the ArcGIS Maps SDK for JavaScript](https://developers.arcgis.com/javascript/latest/get-api/index.html)**: includes a no-build-tools, CDN-based setup like these demos.
- **[ArcGIS Location Platform](https://location.arcgis.com/)**: sign in to manage credentials and services.
- **[Create an ArcGIS API key](https://developers.arcgis.com/documentation/security-and-authentication/api-key-authentication/tutorials/create-an-api-key/location-platform/)**: official step-by-step tutorial, including service privileges and referrer restrictions.

## Takeaway

**Platform first. JavaScript on purpose.**

The goal isn't a JavaScript-free app. It's to stop rebuilding what the browser already knows how to do.

Courtney Yatteau | Developer Advocate, Esri | [GitHub @cyatteau](https://github.com/cyatteau)
