## Inspiration

A small supplier update can create a much larger problem on the factory floor. A delivery moves by a few days, a confirmed quantity drops, and a production planner has to work out which job is affected and whom to contact. We built SupplySignal around that moment: turning a change in a purchase order into a visible, explainable next action.

HackFW's focus on practical industrial systems inspired us to choose one operator and one workflow: a supplier desk that helps keep manufacturing work moving.

## What it does

SupplySignal is a supplier exception desk for manufacturing teams. It imports purchase-order confirmations from CSV files, compares delivery dates and quantities with order commitments and production need dates, and flags critical or watch-level exceptions.

Operators can explore supplier health, follow a delivery timeline, search and filter orders, inspect the facts behind each alert, edit supplier follow-up drafts, save planner notes, and record actions. When a supplier provides a revised confirmation, the operator can update the date or quantity and immediately recalculate risk. An activity log records those changes, and CSV exports make the action plan portable.

## How we built it

We built the interface with HTML, CSS, and JavaScript modules, using a forest-green and cream visual system with responsive layouts and light/dark themes. The decision engine uses transparent rules: an ETA after the production need date or a confirmed quantity below the ordered amount creates a critical exception; a missed promise that still meets the need date becomes a watch item.

CSV validation checks required fields, dates, quantities, and duplicate order identifiers. Browser localStorage preserves the workspace on the current device. We published the source on GitHub and deployed the static application to Vercel.

The current prototype uses template-generated drafts. Live ERP integration and AI extraction from supplier messages are planned next steps.

## Challenges we ran into

One challenge was separating a late supplier promise from a delay that actually misses a production need date. We made both dates visible and used distinct priority levels so operators can understand the difference.

Another challenge was keeping the workflow honest: recording a follow-up does not mean a delivery risk is resolved. We kept the risk visible and made revised confirmations trigger a fresh review. We also worked through CSV validation, browser persistence, and making a detailed operations dashboard usable on smaller screens.

## Accomplishments that we're proud of

We built an end-to-end workflow from importing confirmations to reviewing exceptions, preparing follow-up, updating delivery information, and exporting an action plan. The dashboard explains its alerts using source dates and quantities, and the supplier view, timeline, and priority briefing update together as confirmations change.

We are also proud of combining a polished interface with a small, dependency-free codebase that judges and future pilot partners can run without API keys.

## What we learned

Industrial software becomes more useful when it connects information to an operator's next decision. An alert needs evidence, production context, and a clear action. We also learned to distinguish confirmed facts from assumptions: without inventory and bill-of-materials data, an order exception signals exposure but does not prove a line will stop.

Building the workflow first gave us a clearer foundation for adding AI where it can reduce manual work.

## What's next for SupplySignal

Our next step is source-linked AI extraction of delivery dates and quantities from supplier emails and documents, with human review before updates are accepted. We also plan read-only ERP adapters, inventory and bill-of-materials checks, shared authenticated workspaces, and stronger audit history.

We want to test the workflow with a real supplier desk, measure whether it reduces review and follow-up time, and use that feedback to shape a maintainable pilot. Supplier messages and commitments will remain under human control.
