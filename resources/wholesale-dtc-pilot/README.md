# Wholesale-to-DTC Pilot Records

Three header-only CSV templates for a seller who has shipped by the carton to trade buyers and is now piloting single-parcel orders on Shopify, TikTok Shop or another direct-to-consumer channel. They record how a sold item converts to stock and to parcels, whether each pilot order moved shared stock the way you expected, and how each return was refunded, inspected and restocked.

They are working records, not software, a platform integration, legal advice or a provider agreement. Filling them in does not make a pilot safe to reverse and does not show that any channel or tool is configured correctly; it shows what you expected and what you observed.

## How the templates fit together

`unit-map.csv` defines the conversions. `pilot-checks.csv` records expected and observed results for pilot orders and checkpoints. `returns-decision-record.csv` records the separate refund, inspection and restock decisions for each return. `map_id` links all three.

Every `_ref` column holds an evidence identifier or path, such as a ticket number, screenshot file name or count-sheet ID, never the evidence itself. Use roles and internal IDs, never personal names, contact details or customer data. Dates use `YYYY-MM-DD`; timestamps use `YYYY-MM-DDTHH:MM` with the zone named in `time_zone`.

Write `unknown` when evidence cannot establish a value; leave a cell empty only for steps not yet reached. The files ship empty on purpose. Do not paste in example rows from anywhere else as if they were your own results.

## Three units that are not the same

- **Sales unit**: what the customer buys, such as one listing variant or a bundle.
- **Inventory base unit**: the smallest item you count and store, such as one piece.
- **Parcel**: one physical shipment with its own label.

A supplier case is not a sales unit. A bundle of several base units is one sales unit and may ship as one parcel. One order may become several parcels when its stock sits in more than one location or will not fit one package. Record conversions here instead of assuming one sold item equals one piece equals one parcel.

## How to use

1. Before the first pilot order, add a `unit-map.csv` row for each sales unit and base unit pair in the pilot, and verify the case count against a physical count.
2. Decide which system is authoritative for stock, how the channels are reconciled and which quantity fields you will compare. Write down the expected change for each test.
3. Place a test order on each pilot channel and record a `pilot-checks.csv` row at each checkpoint.
4. Record every pilot return or refund request in `returns-decision-record.csv`, one decision column at a time, as each decision is made.
5. When a check returns `deviation` or `unknown`, set `pause_triggered` as you agreed beforehand and investigate before placing new pilot orders.

## Reading the stock columns

Available, Committed and On hand are different inventory states. They are not expected to be equal, and comparing them with each other is not a test. The test is whether each state changed by the amount you predicted for that checkpoint, on every system that shares the stock. An order placed but not yet fulfilled typically changes Committed and Available before it changes On hand; write your own expected values from your platform's current documentation rather than copying them from this note.

A single matching number does not prove that sync works. A double count can stay hidden until an order is fulfilled, cancelled or returned, so include those checkpoints. One unexplained difference is a reason to pause and recount, not proof of a platform defect.

Reconciliation between channels needs a connector you have verified or a manual process you run. Record which one and point to the evidence that it was checked. These templates do not assume a native integration or automatic sync between any two channels.

## Reading the tracking columns

Record tracking per channel, because each channel has its own tracking and upload rules. Those rules, including any upload deadlines or delivery targets, differ by channel, market and fulfillment model and change over time; check the current channel documentation and do not treat any single deadline as universal. A tracking number with no recent carrier event means no new event has been reported, not that the parcel has stopped.

## Reading the returns columns

Refund, inspection and restock are three decisions. They may happen on different days and in different orders. A refund can be issued before inspection, after inspection or with no item coming back. Each channel can have its own return and refund flow; record the flow actually used. A returned unit is not sellable again until someone assigns it a disposition and writes it back to stock.

## Pausing a pilot

A pause stops new pilot orders and starts an investigation. It does not undo orders already accepted, and cancelling a fulfillment request does not guarantee the warehouse has stopped. Decide beforehand who finishes in-flight pilot orders and reconcile stock before resuming. A clean rollback is not assured by these records, and a wholesale order on the same SKU can still be affected by the pilot, so check both sides.

## Columns

`unit-map.csv`: one row per sales unit and base unit pair; a bundle with three components has three rows sharing one `sales_unit_ref`.

- `map_id`: your ID for the row.
- `channel`: where the sales unit is sold, such as `shopify` or `tiktok_shop`.
- `sales_unit_ref`: your listing, variant or bundle ID on that channel.
- `base_unit_sku`: your internal SKU for the counted base unit.
- `base_units_per_sales_unit`: whole number of base units consumed by one sale of this sales unit.
- `case_ref`: the supplier carton or inner-pack reference for this base unit, blank if not received in cases.
- `base_units_per_case`: whole number of base units in one case.
- `case_count_verified`: `yes` when a physical count confirmed `base_units_per_case`, otherwise `no` or `unknown`.
- `parcel_rule`: `ships_alone`, `may_share_parcel`, `may_split_parcels` or `unknown`; repeat the same value on every row of one `sales_unit_ref`.
- `max_sales_units_per_parcel`: whole number that fits one parcel, blank if not decided.
- `effective_date`: date this conversion applies from.
- `decision_owner_role`: role that approved the conversion.
- `evidence_ref`: count sheet or approval record.

Excludes: prices, costs, supplier identities and stock levels.

`pilot-checks.csv`: one row per order checkpoint or scheduled count.

- `check_id`: your ID for the row; `map_id` links to the unit map.
- `channel`: channel where the test order was placed, blank for a scheduled count.
- `order_ref`: internal order number without customer details.
- `check_type`: `stock_change`, `reconciliation`, `physical_count` or `tracking`.
- `checkpoint`: `before_order`, `after_order`, `after_fulfillment`, `after_cancellation`, `after_return` or `scheduled_count`.
- `quantity_unit`: `base_unit` or `sales_unit`, applying only to the six stock-change columns and `physical_count`. `expected_parcels` and `observed_parcels` are always counts of parcels, not stock or sales units.
- `authoritative_stock_system`: the system you treat as the stock source.
- `reconciliation_method`: `verified_connector`, `manual`, `none` or `unknown`.
- `reconciliation_verified_ref`: evidence that the connector or manual process was checked.
- `expected_available_change`, `observed_available_change`, `expected_committed_change`, `observed_committed_change`, `expected_on_hand_change`, `observed_on_hand_change`: signed whole numbers since the previous checkpoint for the same order, in `quantity_unit`.
- `physical_count`: whole number counted on the shelf, blank unless `check_type` is `physical_count`.
- `expected_parcels`, `observed_parcels`: whole numbers of parcels for the order.
- `tracking_channel`: channel whose order the tracking must reach.
- `tracking_numbers_present`: `yes`, `partial`, `no` or `unknown`.
- `tracking_returned_to_channel`: `yes`, `no` or `unknown`.
- `last_carrier_event_at`: timestamp of the latest carrier event you can see.
- `result`: `as_expected`, `deviation` or `unknown`.
- `pause_triggered`: `yes` or `no`.
- `evidence_ref`, `checked_at`, `time_zone`: evidence, check time and its zone.

Excludes: carrier promises, delivery-time targets and customer contact data.

`returns-decision-record.csv`: one row per return or refund request line.

- `return_id`: your ID; `order_ref` and `map_id` link to the order and unit map.
- `channel`: channel of the original order.
- `return_flow`: `return_then_refund`, `refund_without_return`, `channel_flow`, `chargeback` or `other`.
- `base_units_affected`: whole number of base units covered by the line.
- `refund_decision`: `full`, `partial`, `none`, `pending` or `unknown`.
- `refund_basis`: `before_inspection`, `after_inspection`, `no_item_returning`, `channel_rule` or `unknown`.
- `refund_decided_at`, `refund_owner_role`: when and by which role.
- `item_received`: `yes`, `no`, `not_expected` or `unknown`; `received_at` when it arrived.
- `inspection_result`: `resellable`, `damaged`, `wrong_item`, `incomplete`, `not_inspected` or `unknown`.
- `inspected_at`, `inspection_owner_role`: when and by which role.
- `disposition`: `restock`, `quarantine`, `dispose`, `return_to_supplier` or `undecided`.
- `restocked_base_units`: whole number written back to sellable stock.
- `stock_written_back`: `yes`, `no`, `not_applicable` or `unknown`; `stock_writeback_ref` points to the adjustment.
- `evidence_ref`, `time_zone`: evidence and the zone for this row's timestamps.

Excludes: refund amounts, payment details, reasons stated in customer words and customer identities.

## Source

These templates turn the inventory, order reconciliation, tracking, returns and single-SKU pilot records described in [From Cartons to Single Parcels: The Warehouse Fulfillment Changes a Wholesale Seller Must Make Before Launching Shopify or TikTok Shop DTC](https://asgdropshipping.com/wholesale-to-dtc-fulfillment-operational-changes/) by ASG Dropshipping into blank working files. They contain no ASG operational data and no client examples. Revised 2026-10-03; see `LICENSE.txt`.
