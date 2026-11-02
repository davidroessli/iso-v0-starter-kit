# ISO starter kit for v0 (test)

A small, readable version of ISO's front end ("Wood") for building simple ISO pages with AI tools such as v0. **This is a test**: it isn't an official ISO resource and may change or disappear.

Wood is Bootstrap 5.3 with an ISO layer on top. This kit keeps that split:

| File | What it is | Give it to the AI? |
|---|---|---|
| `css/bootstrap-iso.css` | Bootstrap 5.3.8 compiled with ISO colours, font, breakpoints and component settings (minified) | No, just link it |
| `css/iso.css` | What ISO adds on top of Bootstrap (31 KB, readable) | Yes |
| `tokens/tokens.json` | ISO colours, typography, spacing, breakpoints (W3C design tokens) | Yes |
| `components/*.html` | Standalone examples: top navigation, breadcrumbs, hero banner, text and image, images, card, buttons, footer | Yes |

To see the components rendered, download the repository and open the HTML files in a browser (they load the stylesheets from jsDelivr).

Files are served by jsDelivr straight from this repository. After a change, jsDelivr can take up to 12 hours to pick it up; open `https://purge.jsdelivr.net/gh/davidroessli/iso-v0-starter-kit@main/css/iso.css` (same for any other file) to refresh it immediately.

## Using it in a page

Load both stylesheets, in this order:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/davidroessli/iso-v0-starter-kit@main/css/bootstrap-iso.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/davidroessli/iso-v0-starter-kit@main/css/iso.css">
```

Optional:

```html
<!-- Bootstrap Icons -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
<!-- Bootstrap JavaScript (dropdowns, menus) -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

The Inter font loads automatically from `cdn.iso.org`.

## Running it

Plain HTML, no build step. To serve it locally (Node.js 18 or later):

```bash
npm install
npm run dev
```

Then open <http://localhost:3000>. The server uses `$PORT` when it's set.

### Importing into v0

v0 can import this repository as a project. It needs the Vercel GitHub App to have access to the repository (GitHub → Settings → Applications → Vercel → Configure). After import, v0 commits its changes to a working branch (never to `main`) and Vercel builds a preview of that branch. New pages go next to `index.html` and load the two stylesheets with relative paths (`css/bootstrap-iso.css`, `css/iso.css`).

## Rules for generated pages (interim)

Until the full usage guidelines are written:

- Write plain HTML with Bootstrap 5.3 classes. Don't use Tailwind, shadcn or other UI libraries.
- Reuse the markup from `components/`. Don't add inline styles, custom CSS or new colours.
- Use only colours from `tokens/tokens.json`. Decorative colours (navy, blue, purple…) only exist as `.bg-*` classes.
- `.btn-primary` is the main action, `.btn-outline-primary` the secondary action. `.btn-secondary` is dark red, not grey.
- Breakpoints are ISO's, not Bootstrap's: `sm` ≥ 768px, `md` ≥ 992px, `lg` ≥ 1200px, `xl` ≥ 1400px, `xxl` ≥ 1680px.
- 1rem is 18–20px. Use `h1`–`h6` for headings, not `.fs-*` classes (they don't match ISO sizes).
- The page background is light grey; cards are white with no border.
- Put images in a `<figure>` with an `.img-container`, as in `components/image.html`. Every image needs alt text.
- Start each page with the header from `components/navbar.html` and end it with a footer from `components/footer.html`. Keep the ISO logo as the empty `.logo.isologo` link; the stylesheet draws it.

## Status

- Done: tokens, stylesheets, top navigation, breadcrumbs, hero banner, text and image, images, card, buttons, footer.
- To come: usage guidelines.

The files are generated from Wood's Sass sources; edit them there, not here.
