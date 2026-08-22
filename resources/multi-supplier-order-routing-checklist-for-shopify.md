# Multi-Supplier Order Routing Checklist (Shopify)

A working checklist for Shopify stores routing orders across two or more suppliers or fulfillment apps. Use it before moving real order volume onto a multi-supplier setup, and again whenever a new supplier or fulfillment app is added.

## 1. SKU and location mapping

- [ ] Every variant has a SKU that is unique to the supplier fulfilling it.
- [ ] No two suppliers share a SKU for different physical products.
- [ ] Every variant is mapped to the correct inventory location or fulfillment service.
- [ ] Newly added variants are checked against this mapping before going live.

## 2. Fulfillment-order verification

- [ ] For a multi-supplier order, Shopify generates one fulfillment order per location or fulfillment service, not a single combined fulfillment order.
- [ ] The parent order and its underlying fulfillment orders are both checked, not just the parent order.
- [ ] Each supplier's app or integration imports only the line items assigned to its own fulfillment order.

## 3. Exception ownership

- [ ] Each fulfillment order has an identified owner (fulfillment team, supplier account manager, or app support) for exceptions.
- [ ] Cancelling or retrying one supplier's fulfillment request does not resend the other supplier's line items.
- [ ] A known escalation contact exists for each supplier app's integration issues.

## 4. Controlled test order matrix

Before moving live volume, run and record results for:

- [ ] One test order containing only a supplier-A item.
- [ ] One test order containing only a supplier-B item.
- [ ] One mixed test order containing items from both suppliers.

For each test order, confirm:

- [ ] Correct SKU-to-location mapping held.
- [ ] Expected number of fulfillment orders was created.
- [ ] Each supplier app imported only its assigned line items.
- [ ] Cancel/retry on one supplier's request did not affect the other supplier's items.

## 5. When Shopify splits correctly but a supplier app does not

- [ ] Confirm the fulfillment orders are correctly split inside Shopify first.
- [ ] If a supplier app still imports the full order, treat it as an integration issue on the app's side, not a Shopify data issue.
- [ ] Send the app's support team: the test order ID, the specific fulfillment-order IDs, the affected variant IDs, and a screenshot of the line-item assignment.

## 6. Workaround to avoid

- [ ] Do not duplicate the customer's order to give each supplier a separate copy. It creates two payment records, two tracking numbers, and two refund paths for one purchase.

## Reference

Full write-up with the underlying reasoning and data-model discussion: https://asgdropshipping.com/how-growing-stores-manage-multiple-suppliers-fulfillment-chaos/
