# Double Spoon Salt — Website

A bilingual (Lao/English) one-page website for Double Spoon Salt (ເກືອກາບ່ວງຄູ່), a salt factory in Ban Somsavanh, Xaythany District, Vientiane Capital, Laos.

The site is an information page, not an online shop — it introduces the factory, the people, the production process, and the four kinds of salt made there (iodized table salt, non-iodized hygiene salt, pool salt, and sun-dried industrial salt), and points visitors to phone, WhatsApp, and Facebook to order.

## Files

- `index.html` — the complete site, single self-contained file (CSS and all photos inlined as base64) so it can be opened or hosted anywhere with no build step and no external dependencies besides Google Fonts.
- `assets/` — the original source photos and the logo, kept separately so the page can be edited without extracting images back out of the base64 blobs:
  - `logo.png` — brand seal logo (background removed)
  - `hero-pond.jpg` — evaporation pond hero photo
  - `factory.jpg` — workers raking salt (Story section)
  - `product-*.jpg` — the four product package photos
  - `process-*.jpg` — factory equipment photos (Process section)
  - `certificate.jpg` — Lao Ministry of Health Food and Drug Department food registration certificate for the iodized table salt product

## Editing

`index.html` is hand-authored HTML/CSS with no build tooling. To change a photo, re-encode the new image as a data URI and replace the corresponding `<img src="data:image/...;base64,...">` value; to change copy or layout, edit the HTML/CSS directly. Keep `assets/` in sync with whatever is actually embedded in `index.html` so the repo remains a usable source of truth.

## Deployment

Currently published as a Claude Artifact. The same `index.html` can also be hosted as a static file on any web server, GitHub Pages, Netlify, etc., since it has no server-side dependencies.
