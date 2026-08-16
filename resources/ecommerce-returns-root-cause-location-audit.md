# Ecommerce Returns Root-Cause Location Audit

Use this audit to classify a return by the first point in the operating chain where the problem became visible to someone who could act on it. Do not treat the customer's selected reason code as the root cause without checking the evidence.

## Download The Working Template

[ecommerce-returns-root-cause-location-audit.csv](templates/ecommerce-returns-root-cause-location-audit.csv)

## The Method

1. Start with the customer report, but do not stop there.
2. Collect the order, product, inspection, packing, tracking, and return evidence that exists.
3. Assign one `first_visible_location` from the six locations below.
4. Give the case to the owner who controls that location.
5. Record a corrective action and keep the case open until the same control has been verified.

If there is no product, order, packing, or transit defect, record that conclusion rather than forcing the case into an upstream category.

## Six First-Visible Locations

| Location | What can become visible here | Useful evidence | Likely control owner |
|---|---|---|---|
| `supplier_production_line` | Material, construction, finish, component, or specification faults before the item enters fulfillment | Approved specification, batch or supplier reference, production sample, defect photos | Supplier or sourcing owner |
| `pre_shipment_check` | Product identity, variant, quantity, appearance, measurement, function, or specification mismatch before release | Inspection checklist, approved reference, measurement or function record, hold/rework decision | QC owner |
| `packing_and_labelling` | Wrong variant, wrong quantity, missing component, wrong label, wrong insert, or unsuitable packaging | Pick list, SKU and variant scan, component count, label record, final package photo | Warehouse owner |
| `line_haul_and_carrier` | Transit damage, loss, delivery exception, or route-handling problem after warehouse release | Carrier acceptance, tracking events, parcel condition, delivery evidence, claim record | Logistics owner |
| `customer_unboxing` | The first customer-visible mismatch, damage, missing item, expectation gap, or setup issue | Customer photo or video, listing version, size/specification shown at purchase, unboxing details | Product, merchandising, or customer-experience owner |
| `returns_adjudication` | Reason-code inconsistency, policy issue, preference return, suspected abuse, or a case that cannot be assigned earlier | Return request, support conversation, prior customer history, inspection of returned unit, refund disposition | Returns or customer-service owner |

## Required Record Fields

Every reviewed return should retain enough information for another operator to reproduce the classification:

- Return ID and original order reference
- SKU, variant, market, and supplier or batch when known
- Customer's original wording and selected reason
- First visible location
- Evidence reviewed
- Assigned owner
- Corrective action
- Status: `OPEN`, `INVESTIGATING`, `CORRECTED`, `VERIFIED`, or `HOLD`
- Review date

Do not mark a case `VERIFIED` only because a refund was issued. Verification means the proposed control was checked at the location where the problem first became visible.

## Weekly Review

1. Group open and closed cases by `first_visible_location`, SKU, supplier, market, and route.
2. Separate isolated cases from repeated patterns.
3. Check whether the same symptom is being assigned to different locations without evidence.
4. Select the recurring location that the team can control first.
5. Assign one correction, one owner, and one review date.
6. Recheck later orders against the same control before closing the pattern.

The purpose is not to produce a percentage that looks precise. It is to identify where preventable cases are crossing the chain without an effective interception point.

## Usage Boundaries

- This template is an operational classification aid, not a legal, compliance, fraud, accounting, or carrier-liability determination.
- Preserve the customer's original wording even when the operational classification differs.
- Do not infer a supplier or warehouse fault without evidence.
- Preference returns and policy decisions may have no preventable upstream defect.
- Adapt evidence requirements to the product, market, route, and return policy.

## Supporting Guide

For the complete location model and examples, read [Where Returns Actually Start: A Location Model for Ecommerce Return Causes](https://asgdropshipping.com/returns-are-a-fulfillment-problem-not-only-a-customer-service-problem/).

Prepared by ASG Dropshipping as a practical resource for Shopify and ecommerce operations teams.
