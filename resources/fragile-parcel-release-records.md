# Fragile Parcel Release Records

A blank CSV worksheet for ecommerce operators who need to keep **product acceptance** separate from **finished-parcel checks**. Use one row per examined parcel under one documented packaging revision. The worksheet records evidence and the authorized decision; it does not decide whether an order may ship.

[Download the blank CSV](fragile-parcel-release-records.csv). Save a private working copy before entering operational information. Do not commit completed customer or shipment records to this public repository.

## Before the first row

Agree the product criteria, packaging revision, order configuration and exception owner with the parties doing the work. Record the applicable carrier and destination requirements in your own controlled documents. This worksheet does not supply a universal packaging specification or replace a provider's agreed release process.

A row covers only the units and parcel actually examined. Sampling does not demonstrate that every unit or parcel was inspected. A photograph documents what is visible; it does not prove transport performance, certification, absence of concealed damage or the cause of a later complaint.

## Use the worksheet

1. Identify the parcel, SKU, order configuration and packaging revision using internal references.
2. Record the product check against its criteria, including the extent of examination.
3. Record carton, cushioning, separation and closure checks against that configuration's agreed requirements. Take internal-arrangement evidence before closure when applicable.
4. If a condition is unclear or differs from the specification, record the exception and responsible role. Preserve the original observation when documenting a correction.
5. Recheck a correction before recording the authorized parcel decision. Product acceptance alone is not parcel release. Do not convert an unanswered field into a pass.

This is a recordkeeping aid, not a laboratory test protocol, an ISTA procedure, legal advice or a promise of damage-free delivery. Routine packaging conformance and transport testing are different activities.

## Column dictionary

All `_ref` fields contain internal document or evidence identifiers, not attachments, public URLs, customer names, addresses or tracking credentials. Use a fresh private worksheet for real work.

| Column | Meaning and boundary |
| --- | --- |
| `record_id` | Unique ID for this examination record. |
| `parcel_ref` | Internal parcel reference; no customer details. |
| `sku_ref` | Internal product/variant reference. |
| `order_configuration_ref` | Required quantity, combination or other configuration affecting packaging. |
| `packaging_revision_ref` | The agreed packaging layout/material revision being checked. |
| `product_criteria_ref` | Product acceptance criteria used in this examination. |
| `examination_scope` | Which units and conditions were examined; never imply unexamined units passed. |
| `product_result` | `conforms`, `does_not_conform`, `unknown` or `not_checked`, against the recorded criteria only. |
| `product_evidence_ref` | Evidence supporting that product observation. |
| `carton_result` | Status against the specified carton requirement. |
| `cushioning_result` | Status against the specified cushioning requirement. |
| `separation_result` | Status against any specified item/part separation requirement. |
| `closure_result` | Status against the specified closure requirement. |
| `pack_evidence_ref` | Evidence of the examined arrangement and finished parcel, as applicable. |
| `exception_ref` | Reference to a discrepancy or unresolved condition, or `none_observed`. This is not proof of no hidden defect. |
| `correction_ref` | Record of the correction, `not_needed`, or blank if that step has not occurred. |
| `recheck_result` | `conforms`, `does_not_conform`, `unknown`, `not_checked` or `not_needed` after correction. |
| `recheck_evidence_ref` | Evidence of the recheck; `not_needed` only when no correction/recheck was required. |
| `parcel_decision` | The actual authorized decision: `release`, `hold` or `pending`. No automatic rule is built into the sheet. |
| `decision_owner_role` | Authorized role responsible for this decision, not a personal name. |
| `decision_ref` | Approval or hold record. A sent message alone does not establish approval. |
| `checked_at` | ISO 8601 date/time including offset, for example the format `YYYY-MM-DDThh:mm:ss+hh:mm`; leave blank until recorded. |

For the four packaging result columns, use `conforms`, `does_not_conform`, `unknown` or `not_checked`. Use `not_applicable` only where the recorded specification establishes that a check does not apply. Blank means not yet entered, not accepted. A failed or unknown check remains visible even if a later authorized decision is recorded.

## Provenance

Prepared by ASG Dropshipping with AI assistance; revised 2026-10-12. The field design adapts the editorial distinction between product acceptance and parcel conformance in [Fragile Product Fulfillment: A Product Inspection and Packaging Checklist](https://asgdropshipping.com/fragile-product-fulfillment-packaging-inspection-checklist/). It does not describe measured ASG customer results or certify an existing service.

The CSV contains a header only, with no operational or demonstration rows. See [the rights notice](fragile-parcel-release-records-LICENSE.txt).
