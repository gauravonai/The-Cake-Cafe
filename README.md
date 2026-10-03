# The Cake Studio — website

A single-page site for The Cake Studio (द केक स्टूडियो), Madhuban Colony, Rahatani,
Pimpri-Chinchwad.

Plain HTML + CSS + vanilla JS. No build step, no frameworks, no dependencies.

## Run it

Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Check it

```sh
npx html-validate index.html     # 0 errors expected
```

The page is also designed to work with JavaScript disabled: every section,
the hero photo and the first gallery slide render without it. JS only adds the
carousel, the "today" highlight on opening hours, and the scroll-in animation.

## Structure

```
index.html          the whole site (markup, styles, script)
images/*.jpg        five photos from the shop
```

Images used to be base64-encoded inside `index.html`, which made the file 795 KB
and meant the browser could not cache or lazy-load them. They are now normal
files: `index.html` is ~64 KB and only the hero image loads up front.

## Design

- **Palette** — deep plum `#2A1420`, gold `#C08A3E` (with a darker `--gold-ink`
  `#92631F` for gold *text*, so it meets WCAG AA on cream), blush `#F3DED5`,
  cream `#FDF8F2`, sage `#5F7355`.
- **Type** — Fraunces for display, Inter for everything else.
- All body text is at least 12px; every tappable element is at least 44px tall.

---

## ⚠️ Placeholders to fill in

Everything below is a guess or a stand-in. Search `index.html` for `PLACEHOLDER`
to find each one in context.

| # | What | Where | Current stand-in |
|---|------|-------|------------------|
| 1 | **Menu prices** — all nine | `#menu` cards | ₹550 / ₹650 / ₹600 / ₹575 / from ₹650 / on request / ₹60 / ₹90 / ₹480 per kg |
| 2 | **Opening time** | `#visit` hours table + JSON-LD | `9:00 am` — only the 10 pm close is confirmed |
| 3 | **Weekly day off** | `#visit` hours table | none assumed; open all 7 days |
| 4 | **WhatsApp number** | hero, `#order`, `#visit`, footer, phone bar | assumed same as the shop phone, `+91 97627 24817` — confirm it is on WhatsApp |
| 5 | **Custom-order notice period** | hero note + `#order` | `24 hours` |
| 6 | **Delivery area & charge** | `#visit` service options | "Rahatani and nearby areas — ask when you order" |
| 7 | **Pricing tiers** | `#pricing` | ₹200–300 and ₹300–400 per person, taken from Google's "typical spend" |
| 8 | **Eggless availability** | `#menu` footer, `#pricing`, chips | "on request" for most cakes |
| 9 | **Google Maps place URL** | `#visit` link, map iframe, footer | a *search* by name and address, not the canonical place link — replace with the real one from the shop's Google Business Profile |
| 10 | **Geo coordinates** | JSON-LD | omitted; add `latitude`/`longitude` for better local SEO |
| 11 | **Social links** | not present | add Instagram / Facebook if the shop has them |
| 12 | **Email address** | not present | add one if the shop takes email orders |
| 13 | **Share image** | `og:image` | reuses the Black Forest photo; a wide 1200×630 crop would look better when shared |

The review quotes, the 4.7★ / 34-review figures, the address and the phone number
came from the existing page and were left as they were.
