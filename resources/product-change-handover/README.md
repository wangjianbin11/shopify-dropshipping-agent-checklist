# Product Change Handover Templates

Four header-only CSV templates for recording a product, packaging, label or supplier change on a SKU already stored and shipped by a 3PL, FBA or WFS warehouse. They record which version is approved, what the warehouse was told, what it confirmed and what a real shipment contained.

They are planning aids, not contract terms, legal advice or a compliance procedure, and using them does not guarantee correct shipments. Who sends, acknowledges, executes or verifies each step depends on your provider agreement. Your provider may already have a change process; use it and record outcomes here.

## How the templates fit together

`version-registry.csv` holds one row per approved revision combination. `operating-map.csv` maps each version to batches, allowed orders and an end rule. `warehouse-acknowledgements.csv` logs each instruction sent for a map row and the warehouse response. `first-shipment-verification.csv` checks real shipments against a map row. `version_id` links the registry to the map; `map_id` links the map to the other two.

Every `_ref` column holds an evidence identifier or path, such as a ticket number, never the evidence itself. Use roles and internal IDs, never personal names, contact details or customer data. Dates use `YYYY-MM-DD`.

## How to use

1. Add a registry row when an authorized owner approves a revision combination.
2. Map each affected batch, including inbound, queued, returned and unknown units.
3. Send the instruction through the provider's agreed channel and log the acknowledgement and applied control.
4. Check the first real shipment under each rule.

Write `unknown` when evidence cannot establish a value; leave a cell empty only for steps not yet reached.

## Approval, acknowledgement and shipment evidence

Approval shows that an authorized owner accepted a revision combination and its scope. Acknowledgement shows that the warehouse received the instruction and states the control it applied. First-shipment evidence shows what a real order contained. A sent message, spreadsheet date or receiving scan alone proves none of these later steps.

## Version coexistence

Old and new versions may legitimately coexist. Keep each eligible version's registry row `approved` and give each map row distinct `allowed_order_scope` and `release_or_stop_rule` values. Revision numbers may differ across documents within one registry row. SKU, listing ID, barcode and revision are not interchangeable; changing one does not authorize sale, so check current channel rules first.

## Missing acknowledgement or failed verification

If acknowledgement is missing, keep `ack_status` at `sent` or `unknown`, set `next_check_date` and do not treat the change as live. A missing record is an open question, not proof of warehouse failure. If verification fails or is unclear, record `mismatch` or `unknown` and trace the order through batch, approval, instruction and end rule; a mislabel or mispick remains possible. Hold, release, rework or removal decisions, including safety or eligibility questions, belong to an authorized owner and the actual stock holder.

## Columns

`version-registry.csv`: `version_id` is your ID for one revision combination; `internal_sku` is your own SKU; `channel_listing_id` is the sales-channel listing ID; `barcode_id` is the GTIN, UPC or warehouse label code, blank if unused; `product_revision`, `packaging_revision`, `label_revision` and `qc_revision` are the spec, packaging artwork or material, label and inspection-criteria revisions; `approval_status` is `draft`, `approved`, `superseded` or `rejected`; `approval_ref` points to the approval record and scope.

`operating-map.csv`: `map_id` identifies the row; `version_id` links to the registry; `batch_ref` is the lot, batch or inbound shipment reference; `stock_category` is `on_hand`, `inbound`, `queued_orders`, `returned` or `unknown`; `allowed_order_scope` states which orders this stock may fulfill; `release_or_stop_rule` is the date, batch or order-set condition starting or ending use; `rule_time_zone` applies to date rules, blank otherwise; `disposition_path` is `sell_through`, `parallel`, `hold`, `remove`, `rework` or `undecided`; `decision_owner_role` names the authorized role; `decision_ref` points to its decision.

`warehouse-acknowledgements.csv`: `ack_id` identifies the row; `map_id` links to the map; `instruction_ref` points to the instruction as sent; `submission_channel` is the agreed route, such as portal ticket or account manager; `ack_status` is `not_sent`, `sent`, `acknowledged`, `declined` or `unknown`; `ack_date` is when acknowledged; `ack_ref` points to the reply; `implemented_control` is the control the warehouse reports, such as a separate location or pick rule; `implementation_ref` points to evidence it was applied; `next_check_date` schedules a recheck.

`first-shipment-verification.csv`: `check_id` identifies the row; `map_id` links to the map; `order_ref` is an internal order number without customer details; `shipment_ref` points to the dispatch record; `shipped_batch_ref` is the batch warehouse records link to the shipment, or `unknown`; `expected_version_id` and `observed_version_id` are the allowed and evidenced versions; `check_result` is `match`, `mismatch` or `unknown`; `evidence_ref` points to supporting evidence; `checked_date` is the check date.

## Source

The four templates follow, as planning context, the record groups in [Why a 3PL Does Not Replace Sourcing, QC, Packaging, and Product Development](https://asgdropshipping.com/3pl-sourcing-qc-packaging-product-development/) by ASG Dropshipping: approval of the revision combination, stock and order mapping with an end rule, warehouse instruction and acknowledgement, and a first-shipment check. Revised 2026-10-02; see `LICENSE.txt`.
