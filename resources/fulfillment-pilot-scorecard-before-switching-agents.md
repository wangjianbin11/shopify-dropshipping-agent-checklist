# Fulfillment Pilot Scorecard Before Switching Dropshipping Agents

Use this scorecard to test a new China fulfillment agent before moving live Shopify order volume. The purpose is to verify the complete operational workflow, not only a product sample or shipping quote.

## How To Use This Scorecard

1. Choose a small group of representative SKUs and destination markets.
2. Agree on each test, required evidence, and pass condition before the pilot starts.
3. Record the result as `PASS`, `HOLD`, or `FAIL`.
4. Assign an owner and retest date for every `HOLD` or `FAIL` result.
5. Expand volume only after the corrected workflow passes the same control.

## Pilot Order Matrix

| Test order | Workflow being tested | Required evidence | Result |
|---|---|---|---|
| Core SKU to a primary market | Standard order path | Order event log, QC record, packing evidence, carrier scans | PASS / HOLD / FAIL |
| Multi-variant or bundle order | SKU mapping and kitting | Pick list, component count, variant labels, package photo | PASS / HOLD / FAIL |
| Branded-packaging order | Packaging and insert control | Approved specification, material version, final package photo | PASS / HOLD / FAIL |
| Priority-market order | Route and tracking quality | Shipping service, physical carrier acceptance, tracking timeline | PASS / HOLD / FAIL |
| Address change before dispatch | Exception ownership | Request timestamp, cutoff rule, warehouse stop, corrected label | PASS / HOLD / FAIL |
| Cancellation or partial cancellation | Store-to-warehouse control | Store event, warehouse acknowledgement, inventory correction | PASS / HOLD / FAIL |
| Controlled QC hold | Failure and rework process | Inspection evidence, hold status, disposition, repeated final check | PASS / HOLD / FAIL |
| Inventory mismatch | Stock exception process | Affected order, owner, approved choice, corrected inventory | PASS / HOLD / FAIL |

## 1. Shopify Order Sync

Verify that the information required by the warehouse moves correctly from the store or approved order channel.

- [ ] Correct Shopify order number
- [ ] Correct SKU and variant
- [ ] Correct quantity
- [ ] Correct customer address
- [ ] Correct shipping service or route rule
- [ ] Correct warehouse or fulfillment location
- [ ] Correct payment or release state
- [ ] Correct fulfillment status returned to Shopify
- [ ] Tracking number and link returned to the order
- [ ] Duplicate or edited orders handled under a written rule

**Pass condition:** The order can be traced from Shopify to the warehouse and back without manual reconstruction of critical data.

## 2. Product-Specific QC Evidence

Do not accept a generic “QC completed” status. Define checks that match the product and its risks.

- [ ] Product identity matches the order
- [ ] Variant, size, color, and quantity are correct
- [ ] Appearance is checked against the approved reference
- [ ] Measurements are checked where relevant
- [ ] Function is checked where relevant
- [ ] Included parts and accessories are present
- [ ] Labels and identifiers are correct
- [ ] Packaging version is correct
- [ ] Critical and cosmetic defects are classified separately
- [ ] Failed items have a documented disposition: hold, rework, return, replacement, or seller review
- [ ] Corrected items receive a new final check

**Pass condition:** The evidence shows what was inspected, which specification was used, who inspected it, what failed, and how the item was handled.

## 3. Packaging And Brand Materials

- [ ] Correct packaging specification is attached to the SKU or order
- [ ] Correct insert, label, logo, or thank-you card is used
- [ ] Bundle contents match the approved component list
- [ ] Packaging protects the product for the selected route
- [ ] Low-stock alerts exist for controlled brand materials
- [ ] No unapproved packaging substitution occurs
- [ ] Final package weight and dimensions are recorded when required

**Pass condition:** The delivered package matches the approved version and any shortage or substitution follows a written approval process.

## 4. Carrier Acceptance And Tracking

- [ ] Shipping service matches the order rule
- [ ] Tracking number belongs to the correct parcel
- [ ] Physical carrier acceptance can be verified
- [ ] Tracking link works outside the internal system
- [ ] Status updates are understandable to a customer
- [ ] Delivery result is visible for the tested destination
- [ ] Delay, loss, and return escalation owners are documented

**Pass condition:** The parcel and its tracking events can be followed from warehouse release through the tested customer destination.

## 5. Controlled Exception Tests

Run exceptions deliberately, one at a time, with the partner's knowledge. Do not create false disputes or unsafe shipments.

### Address change

- [ ] Written cutoff is known
- [ ] Request enters the approved channel
- [ ] Picking or labeling stops when the request is still eligible
- [ ] Corrected address reaches the final parcel
- [ ] Shopify or the agreed source of truth reflects the outcome

### Cancellation

- [ ] Full and partial cancellation rules are documented
- [ ] Warehouse acknowledges the request
- [ ] Inventory and payment impact are recorded
- [ ] The order does not ship after an accepted cancellation

### Inventory mismatch

- [ ] Unapproved substitutions are blocked
- [ ] Affected orders are identified
- [ ] The responsible owner is notified
- [ ] Seller-approved choices are presented
- [ ] Inventory is corrected after the exception

### QC failure and rework

- [ ] Failed unit is isolated
- [ ] Evidence is attached
- [ ] Seller disposition rule is followed
- [ ] Replacement or rework is completed
- [ ] Corrected order passes the same final control

**Pass condition:** Each exception has one accountable owner, a traceable evidence trail, and a defined closure state.

## 6. Customer Experience Review

- [ ] Store confirmation shows the correct order and shipping expectation
- [ ] Tracking link works on a customer device
- [ ] Parcel arrives with the correct item and quantity
- [ ] Outer and inner packaging are acceptable
- [ ] Brand materials match the approved version
- [ ] Support can explain an exception with evidence
- [ ] One team or person owns final resolution

**Pass condition:** A customer can understand the order, tracking, delivery, and support outcome without conflicting information.

## 7. Go, Hold, Or No-Go Decision

### Go

- Tested workflows passed.
- Corrected failures passed a retest.
- The next SKU, market, and volume stage are defined.
- The previous route remains available during the transition.

### Hold

- The problem appears fixable.
- An owner and correction plan are documented.
- A retest date is scheduled.
- No additional volume moves before the retest passes.

### No-Go

- Critical order data cannot be controlled.
- QC evidence is not reviewable.
- Exceptions have no accountable owner.
- Compliance, safety, or brand requirements cannot be met.
- The partner cannot support a reversible migration.

## Reference Guide

For the complete methodology, examples, and phased migration sequence, read:

[Test Orders Before Switching China Agent: How to Stress-Test Fulfillment Before Migrating](https://asgdropshipping.com/test-orders-before-switching-private-china-agent/)

Prepared by ASG Dropshipping as a practical resource for Shopify and ecommerce operators evaluating a fulfillment migration.
