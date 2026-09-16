# Double Spoon Salt — Website

A bilingual (Lao/English) one-page website for Double Spoon Salt (ເກືອກາບ່ວງຄູ່), a salt factory in Ban Somsavanh, Xaythany District, Vientiane Capital, Laos.

The site is an information page, not an online shop — it introduces the factory, the people, the production process, and the four kinds of salt made there (iodized table salt, non-iodized hygiene salt, pool salt, and sun-dried industrial salt), and points visitors to phone, WhatsApp, and Facebook to order.

## Files

- `index.html` — the deployable site: a complete, standalone HTML document (doctype, `<meta name="viewport">`, etc.) that references images as separate files in `images/`. This is what's hosted on Vercel. No build step, no server-side dependencies besides Google Fonts.
- `images/` — web-ready photos referenced by `index.html`: resized/re-compressed (quality-preserving, no sharpening/filtering) so mobile doesn't download desktop-sized files. The hero photo ships as four widths (`hero-800.jpg`…`hero-2048.jpg`) selected via `srcset` so phones get a small file and desktops get the full-resolution one. Everything below the first screen uses `loading="lazy"`.
- `assets/` — the original, full-resolution source photos and the logo, untouched, kept so `images/` can be regenerated if the photos ever need to change:
  - `logo.png` — brand seal logo (background removed)
  - `hero-pond.jpg` — evaporation pond hero photo
  - `factory.jpg` — workers raking salt (Story section)
  - `product-*.jpg` — the four product package photos
  - `process-*.jpg` — factory equipment photos (Process section)
  - `certificate.jpg` — Lao Ministry of Health Food and Drug Department food registration certificate for the iodized table salt product
- `vercel.json` — sets a long, immutable cache header on `/images/*` so repeat visits don't re-download photos.

## Editing

`index.html` is hand-authored HTML/CSS with no build tooling — edit copy/layout directly. To change a photo: replace the file in `assets/`, regenerate the matching file(s) in `images/` at the same treatment (resize with high-quality resampling only, no sharpen/contrast/saturation filters — quality should stay visually identical to the original, just sized for how large the photo actually displays), and keep the `<img>`/`srcset` paths in `index.html` pointing at the right filenames.

**Important:** the version of this page published as a Claude Artifact (a separate, single self-contained file with all photos inlined as base64, no doctype/head — the Artifact platform wraps it) is NOT the same file as this repo's `index.html`. Don't copy one over the other — the Artifact version needs to stay a single-file fragment, and this repo's version needs to stay a full document with external images for good mobile performance.

## Deployment

Deployed on Vercel as a static site — `index.html` plus `images/` at the repo root, no build command needed. The page is also published separately as a Claude Artifact for quick sharing (see note above); that copy is maintained independently.
