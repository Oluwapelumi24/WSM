# Mobile Wet Stock Management — Executive Dashboard

Executive Fleet Overview for the Mobile Wet Stock Management (MWSM) platform: live fleet map, product movement, volume reconciliation and management alerts for PMS, AGO and DPK road tankers.

> **Demonstration data.** Every figure, truck, driver and location is generated for illustration and does not represent actual operational results.

## Run locally

It is a single static page with no build step — open `index.html` in a browser.

## Deploy

- **Netlify:** import this repo (no build command, publish directory `.`), or drag the folder onto app.netlify.com/drop.
- **Vercel:** import this repo with Framework preset **Other** and no build command, or run `vercel --prod` in the repo folder.

## Reconciliation logic

- Expected closing = opening + loaded − discharged
- Unexplained variance = expected closing − actual closing
- Reconciled per compartment, then aggregated; percentages are volume-weighted.
- Incomplete trips are provisional and excluded from reconciliation results.

## Connecting real data

All demo data comes from the `api` object in `index.html` (`getSnapshot`, `refresh`, `updateAlert`). Replace those functions with calls to the MWSM platform APIs; the rest of the page only consumes their return shapes.
