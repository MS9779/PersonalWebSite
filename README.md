# PersonalWebSite

## Featured project: StockMitra — Your retail sidekick

StockMitra is a practical, AI-assisted retail operations prototype inspired by a real inventory problem: existing stock can be hard to digitize when not every item can be scanned. A retailer can start with names and counts, add barcodes when useful, and use clear stock signals to plan a possible reorder.

## Try the demo

Open the [StockMitra demo](https://ms9779.github.io/PersonalWebSite/) after its first successful deployment. The application source is in [`stockmitra/`](./stockmitra/).

## What the prototype includes

- Browser-based stock catalog with optional barcode and internal item reference.
- CSV import and export.
- Stock-at-cost, attention flags, and reorder estimates based on saved minimum quantities.
- Vendor directory with external order-page shortcuts and a browser-local purchase ledger with item-level receiving that updates stock.
- POS sales CSV import with catalog matching, units sold, net sales, unmatched-row review, and optional on-hand adjustment after confirmation.
- A guide that explains calculations from the current demo catalog.
- Mobile-friendly, low-distraction interface.

## Why it exists

Independent retailers often have inventory spread across shelves, supplier invoices, and disconnected systems. Before they can benefit from sophisticated forecasts, they need a practical way to record what is already in the store. StockMitra starts there and is designed to grow toward verified supplier and sales connections, stronger inventory controls, and grounded AI guidance.

## Current limits

This is a portfolio prototype, not a production inventory system. It uses invented sample data and browser storage. The built-in guide is transparent, rules-based logic, not a live language model. There is no live POS, supplier ordering, email inbox, payment, authentication, compliance, or forecasting integration. POS CSV files can be imported manually; vendor orders are recorded manually after ordering on the supplier site.

## Deployment

GitHub Pages is configured to use GitHub Actions. The workflow publishes the `stockmitra/` app after relevant pushes to `main`.

## Local use

Open `stockmitra/index.html` in a modern browser. Reset demo data to restore the sample catalog and clear local order, sales, and custom-vendor records. The Vendors & Orders section contains a sample POS CSV to try the sales import. See [`stockmitra/README.md`](./stockmitra/README.md) for the business context, calculations, data fields, and product roadmap.
