# Shad0wo5 Deals — live data

This repo is the live data source for the public Shad0wo5 Deals page
(https://muse.ai/s/shad0wo5-deals-pt6jxgxqxixa8xuv/scD-x3DpbaHCZL0G-B831aqsi13nhjbViXlYOpA9P7Y).

The page fetches `deals.json` from this repo on every visit, so updating
this file updates the live page instantly — no republish needed.

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
