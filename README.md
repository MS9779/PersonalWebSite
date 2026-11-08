# PersonalWebSite

## Featured project: StockMitra — Your retail sidekick

StockMitra is a practical, AI-assisted retail operations prototype inspired by a real inventory problem: existing stock can be hard to digitize when not every item can be scanned. A retailer can start with names and counts, add barcodes when useful, and use clear stock signals to plan a possible reorder.

## Try the demo

Open the published app at the GitHub Pages URL after the first successful deployment. In this repository, the application source is in [`stockmitra/`](./stockmitra/).

## What the prototype includes

- Browser-based stock catalog with optional barcode and internal item reference.
- CSV import and export.
- Stock-at-cost, attention flags, and reorder estimates based on saved minimum quantities.
- A guide that explains calculations from the current demo catalog.
- Mobile-friendly, low-distraction interface.

## Why it exists

Independent retailers often have inventory spread across shelves, supplier invoices, and disconnected systems. Before they can benefit from sophisticated forecasts, they need a practical way to record what is already in the store. StockMitra starts there and is designed to grow toward supplier and sales connections, stronger inventory controls, and grounded AI guidance.

## Current limits

This is a portfolio prototype, not a production inventory system. It uses invented sample data and browser storage. The built-in guide is transparent, rules-based logic, not a live language model. There are no POS, supplier, payment, authentication, purchasing, compliance, or forecasting integrations yet.

## Deployment

The repository includes a GitHub Actions workflow that publishes the `stockmitra/` static app to GitHub Pages when the workflow is enabled. The first run may require the repository's Pages source to be set to **GitHub Actions** in Settings → Pages.

## Local use

Open `stockmitra/index.html` in a modern browser. Reset demo data to restore the original catalog. See [`stockmitra/README.md`](./stockmitra/README.md) for the business context, calculations, data fields, and product roadmap.
