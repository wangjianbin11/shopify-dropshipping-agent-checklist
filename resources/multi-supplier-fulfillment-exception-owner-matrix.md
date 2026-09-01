# Multi-Supplier Fulfillment Exception Owner Matrix

A responsibility matrix for Shopify stores that route orders across multiple suppliers, locations, apps, or fulfillment partners. It complements order-routing tests by making exception ownership explicit.

## Route inventory

| Route ID | Supplier / app | Shopify location / service | SKU scope | Destination scope | Primary owner | Backup owner |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |

## Exception matrix

| Exception | Detects | Decides | Acts | Customer update owner | Evidence required | Escalation deadline |
|---|---|---|---|---|---|---|
| SKU mapping mismatch |  |  |  |  | Order ID, variant ID, fulfillment-order IDs |  |
| Supplier rejects fulfillment request |  |  |  |  | API/app error and affected line items |  |
| One supplier is out of stock |  |  |  |  | Stock proof and replenishment date |  |
| Mixed order partially ships |  |  |  |  | Per-line tracking and shipment status |  |
| QC failure blocks one line |  |  |  |  | QC record, isolation, reinspection |  |
| Address change after allocation |  |  |  |  | Change timestamp and route acceptance |  |
| Duplicate fulfillment import |  |  |  |  | App logs and duplicate order identifiers |  |
| Tracking exists but first scan is missing |  |  |  |  | Dispatch release, pickup, and carrier evidence |  |
| Return affects only one supplier line |  |  |  |  | Return authorization and line ownership |  |

## Control rules

- One order can have several fulfillment owners, but each order line has one active owner at a time.
- Retrying one fulfillment request must not resend another supplier's line items.
- Parent-order status is not sufficient evidence; retain fulfillment-order and line-item identifiers.
- Customer communication must distinguish shipped, waiting, cancelled, and exception lines.
- A shared inbox or team name may receive alerts, but one named person owns the next decision.

## Weekly exception review

| Week | Exception count | Oldest open item | Repeated route failure | Owner gap | Control change |
|---|---:|---|---|---|---|
|  |  |  |  |  |  |

## Limits

This matrix assigns work; it does not repair an app integration or verify supplier performance. Use controlled test orders before changing live allocation.

Source framework: https://asgdropshipping.com/how-growing-stores-manage-multiple-suppliers-fulfillment-chaos/
