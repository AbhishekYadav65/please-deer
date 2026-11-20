# Please.Deer — website template

A static website: plain HTML, CSS and JavaScript. Nothing to build or install.

## Run it

Unzip, open a terminal in the `please-deer` folder, then run **one** of these:

**Python (already on most Macs and Linux; Windows: install from python.org)**

```bash
python3 -m http.server 8080
```

On Windows, if `python3` isn't found, use `python -m http.server 8080` or `py -m http.server 8080`.

**Node.js**

```bash
npx serve -l 8080
```

Then open **http://localhost:8080** in your browser.

> Use a local server like the commands above. Double-clicking `index.html` opens it as a file, and some browsers then block the logo mask and other assets.

## What's inside

```
please-deer/
├── index.html        the whole page: markup, styles (in <style>) and scripts (in <script>)
├── img/              product photos, cut-out jewellery (.webp) and the logo (logo-full.png)
├── fonts/            Cormorant Garamond and Plus Jakarta Sans (self-hosted .woff2)
└── js/lenis.min.js   smooth scrolling library (Lenis 1.1.13)
```

## Where to edit

Everything is in `index.html`:

| What | Where to look |
|---|---|
| Products, prices, materials | `const P=[` near the top of the main `<script>` |
| Collection bubbles (Dostępne, Studniówki…) | `const CAPS=[` |
| Evening 3D gallery pieces | `const RING=[` |
| Customs wire and petal colours | `const WIRES=` and `const PETS=` |
| Day-to-night silk colours | `const ACTS=[` and the rose-gold `const DUSK=` between day and night |
| The light journey (sun right → centre, moon centre → left) | `function journey(` sets the path; `const SUN=` and `const MOON=` set the light colours |
| Text, headings, sections | the HTML inside `<main>` |
| Hero scene (cuff, bubbles, chiffon) | `<!-- ACT I -->` in the HTML; in the CSS, `.piece` (`--px`, `--py`, `--ph`, `--rot`) and the `.b-*` bubble classes, with phone positions in the `max-width:900px` block |
| Atelier journal reel (slides sideways; the page still scrolls down) | `<section class="process"` in the HTML; behaviour in the `journal reel` script block |
| Shop / Collections dropdowns | `<nav class="nav-links">` at the top of `<body>` |

To add a product, put a 720×900 `.webp` in `img/` and add an entry to `P` using the file name without the extension.

## Notes

- Prices, sizes, delivery times and some copy are sample content. Check them before launch.
- Checkout, newsletter, sign-in and custom-request forms show a preview message only. Connect them to your store (Shopify, WooCommerce, Stripe) or email service when you go live.
- The bag is saved in the visitor's browser (localStorage).
- Smooth scrolling, the 3D motion and the auto-turning gallery switch off for visitors who set "reduce motion" on their device.
- The light follows the scroll with a gentle delay, so it drifts rather than jumps. Headings rise word by word, photographs open like a curtain, and buttons lean slightly toward the cursor. All of this is off for "reduce motion".
