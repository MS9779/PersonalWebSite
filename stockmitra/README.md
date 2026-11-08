# StockMitra — Your retail sidekick

StockMitra (“stock friend”) is an independent portfolio prototype for small retailers. It explores how a store can build a useful inventory record even when much of its existing stock cannot be scanned, then improve that record over time and use it to make more informed buying decisions.

## Why this project exists

The idea came from a real operating problem noticed while working in a gas station: a store may be able to scan new deliveries, but scanning and cataloging every item already on the shelf is often impractical. That problem is the starting use case, not the product boundary. The longer-term audience is independent retail, including convenience stores and liquor stores, with room to adapt to other small shops.

An inventory tool is useful only if it fits the way a store actually starts and runs. StockMitra lets a user begin with an item name, pack size, quantity, and optional cost. A barcode can be added later. The product then makes the recorded information easier to review and turns simple stock rules into understandable prompts.

## What a visitor can try

- Review a sample store dashboard with stock value, items needing review, reorder estimates, and inventory-record completeness.
- Browse and filter a product catalog, including manual items without a barcode.
- Add an item with a simple form. A barcode is optional; a reference code is generated automatically.
- Import a CSV inventory file and export the current catalog or buying list.
- Review replenishment suggestions based on the quantity on hand and saved minimum level.
- Open sample vendor sites in a separate tab, then record a purchase order with date, amount, items, and confirmation number.
- Review and export a browser-local purchase ledger; cycle sample order statuses from placed to confirmed to received.
- Import POS sales CSV rows, group matched items by catalog entry, and see units sold, net sales, and unmatched rows for cleanup.
- Ask the built-in guide questions about reorder needs, recorded cash by category, or incomplete records.
- Edit an item's on-hand count and reset the browser's sample data.

## How the first version works

The prototype is a responsive, browser-only web app built with HTML, CSS, and JavaScript. It stores the sample catalog in local browser storage. No account or server is required to explore the demo.

The buying calculation is deliberately simple and visible:

```text
suggested quantity = saved minimum stock − current on-hand quantity
estimated order cost = suggested quantity × saved unit cost
```

Suggestions are estimates for a person to review. This version does not place orders, change prices, or assume that the retailer should buy every suggested item. Vendor cards are shortcuts to supplier sites; a retailer may need a vendor account and a custom link may be required for the account-specific order screen. Purchase history is logged at the order level in this prototype; line-by-line receiving reconciliation is a later step.

## The AI approach

The guide in this prototype is a transparent, rules-backed assistant. It answers from the sample catalog and shows the evidence behind its response. It is not connected to a hosted language model, point-of-sale system, sales history, or supplier feed. That is intentional: the current demo demonstrates the product workflow without suggesting that simulated answers are live AI or verified business advice.

A production AI feature should be grounded in a retailer's own verified data, respect staff permissions, log important recommendations, explain uncertainty, and leave purchasing decisions with the owner. A later model integration can improve natural-language questions and summaries after the data model and customer need are validated.

## Roadmap to a product someone could use

1. **Validate the workflow:** observe several independent store owners doing an opening count and receiving a delivery; revise the form and item model around how they work.
2. **Make store data durable:** add sign-in, a secure backend, store and staff roles, backups, and an audit trail before storing real business data.
3. **Improve item onboarding:** support distributor invoices and spreadsheet templates, optional barcode lookup, case-to-unit conversion, and duplicate review. Keep manual entry available.
4. **Connect purchase confirmations:** with clear consent, connect a business inbox or accept forwarded order emails, extract vendor, items, quantities, cost, and order status, then ask the owner to confirm uncertain matches. Keep an auditable source link to the original message.
5. **Connect POS sales:** begin with CSV import or one supported POS integration. Reconcile sold units with received orders and counted on-hand stock; flag mismatches instead of silently changing counts.
6. **Build useful forecasting:** use dated sales, inventory snapshots, supplier lead times, seasonality, and promotions. Show assumptions and confidence with each suggestion.
7. **Test a paid offer:** interview target stores, run a small supported pilot, measure time saved and ordering decisions improved, then validate a subscription and optional setup service.

The first customer group is convenience and liquor stores because they fit the observed inventory problem. The architecture and language should stay adaptable; the goal is not to hard-code the product to one store type.

## What this prototype does not do

- It does not connect to a live POS service, supplier account, email inbox, payments, or language model. POS CSV files are imported manually.
- The vendor page uses sample suppliers and example public links. Order records are entered manually and stored in this browser only. It cannot read purchase emails or securely log in to supplier portals.
- It does not verify inventory counts, sales, costs, supplier availability, local regulations, or expected profit.
- It does not place orders, make price changes, or replace age-verification or point-of-sale systems.
- Sample records are invented for demonstration. Do not treat the sample numbers as a store forecast.

## Run it

Open `index.html` in a modern browser. The demo uses local storage for inventory, purchase-history, vendor, and imported sales data. Use the reset buttons to restore the sample catalog or purchase ledger. Sales imports do not silently change on-hand quantities.

### CSV import columns

The importer requires one item-name column (`name`, `item`, `product`, or `product name`). It also recognizes optional columns for category, pack/size, quantity/on hand, cost, selling price, minimum/reorder point, and barcode/UPC/SKU. Import only data you have permission to use.

### POS sales CSV columns

The sales importer requires an item identifier (`item`, `name`, `product`, `product name`, `SKU`, `UPC`, or `barcode`) and a quantity (`qty`, `quantity`, `units`, or `units sold`). Date and net sales/revenue columns are optional. Rows match on exact product name, internal StockMitra ID, or barcode; unmatched rows stay visible and are not discarded. The import is a sales summary, not an inventory adjustment.

## Design direction

The visual reference is editorial and high contrast, but the product UI stays calm and task-focused. Store staff often use inventory tools while busy, so the interface favors readable numbers, short explanations, familiar actions, responsive layouts, and low-motion transitions over decorative effects.

## Project status

**Working concept prototype.** The screens and local interactions demonstrate the product direction. A real commercial service still needs customer validation, durable storage, authentication, security review, integrations, and a supported AI architecture.
