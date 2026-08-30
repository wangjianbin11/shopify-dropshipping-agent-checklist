# Supplier Blackout Order-Line Triage Template

A blank operating worksheet for Shopify and ecommerce teams whose supplier has stopped responding. It separates three questions that are easy to mix together:

1. What can be verified for each customer-paid order line?
2. How difficult is each affected SKU to move to another supply path?
3. What customer promise is already running?

Copy the tables into your own spreadsheet, database, or incident workspace. Enter one row per customer order line, not one row per order. The companion CSV provides the same core fields in a flat format.

Nothing in this template is a completed ASG record, customer case, legal conclusion, or performance claim.

## 1. Incident control

| Field | Value |
|---|---|
| Incident ID |  |
| Incident owner |  |
| Supplier legal / trading name |  |
| Last verified supplier response |  |
| New non-essential purchase commitments paused at |  |
| Next management review |  |

## 2. Verified exposure by order line

| Customer order ID | Line item | SKU | Supplier PO ID | PO line | Customer paid date | Supplier payment state | Amount paid | Currency | Handover evidence type | Handover reference | Carrier first acceptance event | Verified exposure state | Missing evidence | Evidence owner | Next evidence check |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

Use exactly one current exposure state per line:

- **Uncommitted:** no supplier payment and no verified irrevocable purchase commitment for this line.
- **Financially committed:** a deposit or full payment cleared, but no verified handover evidence exists.
- **Logistically committed:** a pickup, forwarder, warehouse, loading, or manifest record exists, but normal carrier movement is not yet verified.
- **In transit:** independently checkable carrier acceptance or movement events exist.
- **Evidence incomplete:** the available records do not establish payment, handover, or transport status.

Do not classify a line from a purchase order alone. A PO records a commercial agreement, not proof that money cleared. Do not classify a line as In transit from a tracking number alone when carrier acceptance or movement cannot be verified.

## 3. Customer commitment clock

| Customer order ID | Line item | Promised ship date | Promised delivery date | Current clock state | Customer informed | Customer choice recorded | Realistic re-source ship date | Refund / cancellation / dispute risk | Communication owner | Next customer update |
|---|---|---|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |

Suggested clock states are `within_promise`, `at_risk`, and `missed`. These are operational labels, not statutory deadlines or platform rules. Record the actual promise made to the customer and any choice the customer has accepted.

## 4. SKU switching resistance

| SKU | Spec pack status | Approved sample | Packaging version / owner | Tooling owner / location | GTIN / label registration | Compliance document / holder | Backup supplier qualified | Test fulfillment completed | Switching tier | Missing dependency | Recovery owner | Earliest realistic release date |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |

Use one switching tier per SKU:

- **Ready:** a qualified backup, complete spec pack, approved sample, and tested fulfillment or capacity path exist.
- **Rebuild Required:** the product can be reproduced, but packaging, labels, samples, testing, compliance, or listing assets must be rebuilt.
- **Controlled or Locked:** tooling, proprietary components, firmware, IP, certification-holder constraints, exclusive materials, or unrecoverable assets prevent a normal purchase-order switch.

A quote from another supplier does not make the SKU Ready. Take the highest resistance across the components required to ship the complete product correctly.

## 5. Evidence request log

| Request ID | Order / PO / SKU | Evidence requested | Requested from | Requested at | Response due | Evidence received | Independently checked by | Check result | Storage reference |
|---|---|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Name the missing document. Avoid labels such as `supplier proof` when the real request is a bank-cleared payment record, signed pickup receipt, warehouse intake, house air waybill, or carrier acceptance event.

## 6. Decision and action queue

| Priority | Customer order ID | Line item | SKU | Exposure state | Switching tier | Clock state | Current decision | Next action | Named owner | Due at | Evidence required before closure | Closure evidence |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |  |  |  |

The decision must be made from the intersection of exposure, switching resistance, and the customer clock. A line can be financially recoverable and still miss the customer promise. A line can also have goods moving and therefore be unsuitable for immediate duplicate re-sourcing.

## 7. Closure check

Do not close the incident until each affected line has an evidence-backed terminal state:

- [ ] Supplier payment status reconciles to the bank or payment provider.
- [ ] Shipment status is supported by a handover or carrier record, or the missing evidence is explicitly recorded.
- [ ] Every affected SKU has a switching tier and named missing dependencies.
- [ ] Every customer commitment is marked within promise, at risk, or missed.
- [ ] Customer communication and choices are recorded where required.
- [ ] Each action has an owner, due time, and closure evidence.
- [ ] Legal, payment, safety, or compliance questions are escalated to the appropriate qualified party.
- [ ] Failed and superseded records remain preserved; history has not been overwritten.

## Limits

This template does not determine legal title, recover supplier payments, prove fraud or insolvency, set a universal refund deadline, or guarantee that an alternative supplier can rescue an order. Payment, contract, safety, regulatory, and customer-remedy decisions may require your bank, payment provider, marketplace, insurer, or qualified counsel.

Source and operating rationale: https://asgdropshipping.com/dropshipping-supplier-stopped-responding/
