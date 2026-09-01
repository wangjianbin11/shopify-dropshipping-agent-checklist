# CJdropshipping Migration Order Cohort Checklist

A platform-neutral migration checklist for a Shopify store moving order volume away from a CJdropshipping workflow while keeping old and new fulfillment responsibilities clear.

## Fixed cohort rule

Write one rule that decides which provider owns each order. Use an immutable event such as paid-at time, order number boundary, or explicit migration tag.

| Cohort | Rule | Fulfillment owner | Final order expected | Exception owner |
|---|---|---|---|---|
| Legacy cohort |  |  |  |  |
| New cohort |  |  |  |  |

Do not use a rule that can change after allocation, such as whichever provider imports first.

## Before the cutover

- [ ] Export or record every open legacy order and its line-item status.
- [ ] Separate unfulfilled, partially fulfilled, shipped, cancelled, returned, and disputed orders.
- [ ] Freeze the SKU and variant mapping version used for the new route.
- [ ] Run single-SKU, mixed-SKU, address-change, cancellation, and retry test orders.
- [ ] Confirm the new route imports only its assigned cohort.
- [ ] Confirm the old route will not auto-import the new cohort.
- [ ] Define who answers legacy tracking and after-sales questions until closure.

## Cutover control log

| Check time | Last legacy order | First new-route order | Duplicate imports | Missing imports | Wrong SKU / address | Decision owner |
|---|---|---|---:|---:|---:|---|
|  |  |  |  |  |  |  |

## Open legacy order ledger

| Order ID | Paid at | Lines | Fulfillment state | Tracking / exception | Current owner | Next action | Due time |
|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |

## Expansion gate

- [ ] No order line is accepted by both routes.
- [ ] No order line is owned by neither route.
- [ ] Legacy exceptions remain visible after new-route activation.
- [ ] New-route QC, packaging, dispatch, pickup, and first-scan evidence can be retrieved.
- [ ] The rollback owner can stop allocation without recreating customer orders.
- [ ] The migration remains reversible until the pilot cohort is reviewed.

## Limits

This checklist does not represent or audit CJdropshipping and is not a claim about any provider's current service. It is a migration-control tool for store operators.

Source framework: https://asgdropshipping.com/how-to-switch-from-cjdropshipping-without-disrupting-orders/
