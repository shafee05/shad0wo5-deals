# Shad0wo5 Deals — live data + public site

This repo is the live data source AND the public site for Shad0wo5 Deals:
https://shafee05.github.io/shad0wo5-deals/ (GitHub Pages, served from `main`).

`index.html` fetches `deals.json` from the same site on every visit, so
updating this file updates the live page instantly — no republish needed.
(The earlier muse.ai page is retired: its hosted fetch of this repo was
blocked, so it kept showing the built-in 26 Nov copy.)

## Format

`deals.json`: `{ "updated": "YYYY-MM-DD", "deals": [ ... ] }`

Each deal: `id`, `name`, `brand`, `store` (Myntra/AJIO), `category`,
`price` (number, INR), `mrp` (number), `discount` (number, %),
`rating` (string, may be empty), `image` (raw.githubusercontent URL),
`buy` (EarnKaro profit link), `added` (YYYY-MM-DD).

## Daily routine

- Add 10 new deals per day; keep only the last 7 days (drop older deals
  and their images).
- Product images live in `images/`, named `deals-YYYY-MM-DD-<slug>.jpg`.
- Prices are verified live on Myntra/AJIO before adding; buy links are
  EarnKaro profit links created at earnkaro.com.
