# SupplySignal — HackFW submission draft

## Tagline
Small signals. Stronger operations.

## Track
Supplier Relationship Management

## Problem
A revised supplier delivery date can quietly become a production problem. Order confirmations, planner notes, and follow-up actions often live in separate places, making it hard to see which purchase-order lines need attention first.

## What we built
SupplySignal is a supplier exception desk that imports purchase-order confirmations, flags short quantities and delivery delays, links order lines to production job need dates, and prepares editable follow-up drafts for human review. Operators can update confirmations, recalculate risk, record follow-up actions, save planner notes, filter the desk, and export an action plan.

## How it works
The browser compares each confirmed ETA with the promised date and production need date. A short quantity or ETA after the need date is critical; a late promise that still meets the need date is a watch item. The app shows the facts behind each classification. The supplier view summarizes current order-line exceptions, and the timeline arranges confirmed arrivals by date.

## Built with
HTML, CSS, JavaScript modules, browser localStorage, CSV import/export, and static hosting. No runtime dependencies or API keys are required.

## What is real today
CSV ingestion, validation, prioritization, editable confirmations, risk recalculation, notes, draft generation, action logging, search/filtering, export, and theme switching are implemented. The bundled data is fictional. Follow-up text is template-generated, not an AI model response. Recording an action does not send a message.

## Next pilot step
Read-only ERP ingestion, source-linked AI extraction from supplier emails, inventory/BOM-aware impact, authenticated shared storage, and human approval for commitments.

## Required human steps
- Confirm all participants have registered at https://talent.fwtx.city/.
- Confirm in-person Demo Day attendance and event details with the organizer.
- Upload the demo video to a judge-accessible video host and add the final URL.
- Review and submit the project on the organizer's Devpost page.
- Confirm eligibility and any changes to track requirements with the organizer. The pasted brief lists five lanes but its submission checklist names only three tracks.

## Media
The project cover is an AI-generated illustration of a manufacturing supplier network. Screenshots show the actual app. The walkthrough video is assembled from captured app screens with captions; it is not a continuous real-time recording.
