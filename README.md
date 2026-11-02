# ISO starter kit for v0 (test)

A small, readable version of ISO's front end ("Wood") for building simple ISO pages with AI tools such as v0. **This is a test**: it isn't an official ISO resource and may change or disappear.

Wood is Bootstrap 5.3 with an ISO layer on top. This kit keeps that split:

| File | What it is | Give it to the AI? |
|---|---|---|
| `css/bootstrap-iso.css` | Bootstrap 5.3.8 compiled with ISO colours, font, breakpoints and component settings (minified) | No, just link it |
| `css/iso.css` | What ISO adds on top of Bootstrap (31 KB, readable) | Yes |
| `tokens/tokens.json` | ISO colours, typography, spacing, breakpoints (W3C design tokens) | Yes |
| `components/*.html` | Standalone examples: buttons, card, hero banner | Yes |

Rendered examples: <https://davidroessli.github.io/iso-v0-starter-kit/>

## Using it in a page

Load both stylesheets, in this order:

```html
<link rel="stylesheet" href="https://davidroessli.github.io/iso-v0-starter-kit/css/bootstrap-iso.css">
<link rel="stylesheet" href="https://davidroessli.github.io/iso-v0-starter-kit/css/iso.css">
```

Optional:

```html
<!-- Bootstrap Icons -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
<!-- Bootstrap JavaScript (dropdowns, menus) -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
```

The Inter font loads automatically from `cdn.iso.org`.

## Rules for generated pages (interim)

Until the full usage guidelines are written:

- Write plain HTML with Bootstrap 5.3 classes. Don't use Tailwind, shadcn or other UI libraries.
- Reuse the markup from `components/`. Don't add inline styles, custom CSS or new colours.
- Use only colours from `tokens/tokens.json`. Decorative colours (navy, blue, purple…) only exist as `.bg-*` classes.
- `.btn-primary` is the main action, `.btn-outline-primary` the secondary action. `.btn-secondary` is dark red, not grey.
- Breakpoints are ISO's, not Bootstrap's: `sm` ≥ 768px, `md` ≥ 992px, `lg` ≥ 1200px, `xl` ≥ 1400px, `xxl` ≥ 1680px.
- 1rem is 18–20px. Use `h1`–`h6` for headings, not `.fs-*` classes (they don't match ISO sizes).
- The page background is light grey; cards are white with no border.

## Status

- Done: tokens, stylesheets, buttons, card, hero banner.
- To come: image, top navigation, breadcrumbs, text + image layout, footer, usage guidelines.

The files are generated from Wood's Sass sources; edit them there, not here.
