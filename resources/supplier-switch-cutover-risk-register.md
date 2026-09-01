# Supplier Switch Cutover Risk Register

A copyable risk register for ecommerce teams moving active order volume from one supplier or fulfillment partner to another. Use it before the first migrated order and keep it open until the final old-supplier order is closed.

## Cutover identity

| Field | Value |
|---|---|
| Cutover owner |  |
| Old supplier / agent |  |
| New supplier / agent |  |
| Pilot SKUs |  |
| Pilot order cohort |  |
| Planned start |  |
| Rollback decision deadline |  |

## Risk register

| Risk ID | Risk | Early warning signal | Preventive control | Trigger for stop / rollback | Owner | Status | Evidence |
|---|---|---|---|---|---|---|---|
| SW-01 | Wrong SKU or variant mapping | Test order imports a different variant | Freeze and compare SKU map before migration | Any customer order routes to the wrong physical item |  |  |  |
| SW-02 | Inventory promise is not real | Supplier cannot show count, location, or replenishment date | Verify saleable stock and replenishment source | Stock proof is missing for a live SKU |  |  |  |
| SW-03 | QC standard changes during handoff | New supplier uses an undefined or different pass rule | Version the SKU QC standard and run sample evidence | Required checkpoint is absent or fails |  |  |  |
| SW-04 | Packaging is not repeatable | Pilot pack differs from approved specification | Approve one packaging specification and evidence set | Branding, label, insert, or protection is wrong |  |  |  |
| SW-05 | Dispatch events become invisible | No owner can produce release, pickup, or first-scan proof | Define event owner and evidence deadline | Dispatch status cannot be independently reconstructed |  |  |  |
| SW-06 | Old and new suppliers both fulfill | Duplicate import or unclear order ownership | Use a dated cohort rule and one owner per order line | The same line is accepted by two fulfillment routes |  |  |  |
| SW-07 | Returns and exceptions have no owner | Customer case moves between teams without resolution | Name one exception owner for each cohort | Open exception has no owner or next action |  |  |  |

Add product-specific risks rather than deleting the baseline rows.

## Pilot gate

- [ ] The pilot includes the real destination mix and packaging configuration.
- [ ] Every pilot order has an order ID, SKU, supplier, QC record, dispatch record, tracking number, and exception owner.
- [ ] Old-supplier orders and new-supplier orders are distinguishable by a fixed cohort rule.
- [ ] The rollback owner can stop new allocation without duplicating orders.
- [ ] No performance promise is based on one successful parcel.

## Decision record

| Decision | Date | Evidence reviewed | Open risks accepted | Owner |
|---|---|---|---|---|
| Continue pilot / expand / hold / roll back |  |  |  |  |

## Limits

This register organizes operational evidence. It does not verify a supplier by itself and does not guarantee delivery, quality, customs, marketplace, or customer-service outcomes.

Source framework: https://asgdropshipping.com/research/supplier-switch-fulfillment-bottleneck-report/
