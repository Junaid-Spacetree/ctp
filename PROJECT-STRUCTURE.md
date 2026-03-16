# Static Site – Cleaned Project Structure

This document describes the cleaned static HTML website after conversion from the HTTrack WordPress mirror.

## Summary of Changes

- **Removed:** All WordPress-specific files and references (wp-json, wp-includes, xmlrpc, rsd.xml, generator meta, wp-emoji, wp-embed, API/RSD/oembed links).
- **Removed:** HTTrack redirect files (`index2ee9.html` and similar), `feed/` folders, `comments/` folder, and glyphicons `.html` font artifacts.
- **Updated:** All asset URLs to relative paths (`wp-content/...` from root, `../wp-content/...` from subfolders).
- **Updated:** Navigation links to local paths (e.g. `/about/` → `about/index.html`).
- **Neutralized:** Contact form and lightbox AJAX (no server calls); forms submit to `#` for static display.
- **Kept:** Contact email `ohtl@ctp.com.sa` in footer/header as displayed contact info (change via find-replace if needed).

## Final Project Structure

```
CTP-Saudi/
├── index.html                          # Homepage
├── about/
│   └── index.html
├── career/
│   └── index.html
├── contact/
│   └── index.html
├── trading/
│   └── index.html
├── gallery/
│   └── index.html
├── qhse-policy/
│   └── index.html
├── mission/
│   └── index.html
├── automation-control-system/
│   └── index.html
├── fire-alarm-system/
│   └── index.html
├── pump-systems/
│   └── index.html
├── mechanical-electrical-and-plumbing-mep-works/
│   └── index.html
├── transformer-oil-filtration/
│   └── index.html
├── tower-foundation-ohtl/
│   └── index.html
├── hv-ehv-cable-solution/
│   └── index.html
├── materials-trading-service-2/
│   └── index.html
├── high-voltage-insulator-coating-hvic/
│   └── index.html
└── wp-content/                         # Theme & plugin assets (css, js, fonts, images, uploads)
    ├── plugins/
    │   ├── contact-form-7/
    │   │   ├── includes/css/
    │   │   ├── includes/js/
    │   │   └── images/
    │   ├── crelly-slider/
    │   │   ├── css/
    │   │   ├── js/
    │   │   └── images/
    │   └── responsive-lightbox/
    │       ├── assets/tosrus/css/
    │       ├── assets/tosrus/js/
    │       ├── assets/infinitescroll/
    │       └── js/
    ├── themes/ctpthemes/
    │   ├── css/                        # base, bootstrap, common, font-awesome, header, layout, reset, style
    │   ├── js/                         # bootstrap.min, jquery.min, modernizr
    │   ├── fonts/                      # Font Awesome (eot, svg, ttf, woff, woff2)
    │   ├── images/                     # Theme images
    │   └── style.css
    └── uploads/
        └── 2018/
            ├── 07/                     # Banners, favicon, clients, etc.
            └── 09/                     # Service images, logos
```

## Asset Paths

- **From root (e.g. `index.html`):** `wp-content/themes/ctpthemes/...`, `wp-content/plugins/...`, `wp-content/uploads/...`
- **From a subfolder (e.g. `about/index.html`):** `../wp-content/...`
- **Internal links:** `index.html` (same folder), `about/index.html`, `contact/index.html`, etc.

## How to Run

1. Open `index.html` in a browser (file:// or via any static server).
2. All pages and assets load from the local `wp-content` tree; no external requests except Google Fonts (Heebo).

## Notes

- **Contact forms:** Forms are present but do not submit to a server; they are for static display only.
- **Lightbox/gallery:** Responsive Lightbox (Tosrus) runs locally; no AJAX calls.
- **jQuery:** Served from `wp-content/themes/ctpthemes/js/jquery.min.js` (wp-includes references removed).

