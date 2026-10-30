# SupplySignal — Supplier Exception Desk

HackFW track: Supplier Relationship Management.

A browser-based prototype for a supplier operations desk. It imports purchase-order confirmations, flags late and short deliveries, connects each line to a production job, and prepares editable supplier follow-up drafts. A human records the action and exports a plan.

## Run

Requires Python 3. From this directory run `python -m http.server 8000 --directory dist`, then open http://localhost:8000. No dependencies or keys are required. Alternatively serve `dist` with any static web server.

## Demo in 90 seconds

1. Review the sample critical order lines on the exception desk.
2. Open PO-1051. Its control boards arrive four days after production needs them.
3. Review the source dates and the generated follow-up. Edit the wording and download it.
4. Record the follow-up. Show that the action is logged while the risk remains visible.
5. Export the action plan, then download the CSV template and import an edited copy.

## Data contract

CSV columns: `po,supplier,part,ordered,confirmed,due,eta,job,need,units`. Dates use YYYY-MM-DD; quantities are nonnegative integers. One unique PO identifier per row. Use a line-specific identifier for multi-line purchase orders. Import replaces the dataset and clears previous actions. The included template contains five fictional orders.

## Decision logic and limits

Critical means ETA is after the job need date or confirmed quantity is less than ordered quantity. Watch means ETA is after the promised date but not after the job need date. Otherwise the order is on track. No inventory, BOM, partial-receipt, calendar, alternate-sourcing, or financial-impact calculation is performed. `units` is descriptive job output, not calculated production loss. Dates are compared as calendar days.

This version uses transparent rules and template-generated text, not an AI model. No live ERP, email, payment, authentication backend, or multi-user sync is connected. Browser localStorage persists records on the current device; exports provide a portable copy. Do not use this prototype as a production system of record. Google Fonts is optional; system fonts work offline.

## Next pilot milestone

Add read-only ERP ingestion, inventory-aware BOM impact, authenticated shared storage, and grounded AI extraction of supplier confirmations with source evidence. Keep supplier commitments behind human review.

## Submission work remaining

Create a public GitHub repository, record the demo, register participants in the Fort Worth talent network, and confirm Demo Day attendance. Hosting alone does not satisfy the public repository requirement.

## Dashboard update

Adds a priority briefing, supplier health breakdown, delivery timeline, supplier and workflow filters, light/dark themes, planner notes, and editable delivery confirmations. Saving a revised confirmation recalculates risk and reopens follow-up review. All changes remain browser-local. Supplier health is a count of current order-line exceptions, not a historical performance score.

