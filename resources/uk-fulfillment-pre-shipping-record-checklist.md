# Pre-Shipping Record Checklist — China to Great Britain (B2C)

A fill-in template for the three records that must exist **before** you take orders shipping from China to consumers in Great Britain.

**Scope:** Great Britain only — England, Scotland, Wales. **Northern Ireland needs separate review**; do not reuse a completed GB checklist for an NI destination.

**Status:** operational guidance for organising your own records. **Not tax or legal advice.** Nothing here decides your registration position, reaches a legal conclusion, or certifies compliance. Rows marked `[tax adviser]` require confirmation from a qualified adviser working from your own facts.

**Owner labels:** `[seller]` · `[tax adviser]` · `[fulfillment partner]`

**How to use:** fill every field, resolve every `FAIL`, then run the pre-launch gate. Re-run after changes.

---

## Record 1 — Tax and border-charge route

Keep four things distinct. Do not merge them into one "VAT handling" note: **point-of-sale VAT**, **charges arising at the border**, **customs/declaration data supporting both**, and **the future duty reform**.

The GBP 135 point-of-sale VAT framing below applies to B2C goods shipped from China to consumers in Great Britain.

### 1.1 Consignment composition and value `[seller]`

```
What travels together as one consignment: ____________________
Consignment value: __________  Currency: ______
Source system for this value: ____________________
```

**Validate:** value carries an explicit currency; source system named; the composition rule is written down, not decided per order by whoever packs.
**FAIL if:** currency implicit, or composition varies without a rule.

### 1.2 Point-of-sale VAT owner and registration position `[seller]` + `[tax adviser]`

```
Who accounts for point-of-sale VAT: ____________________
Registration position (as confirmed on our own facts): ____________________
Confirmed by: ____________________   Date: __________
Route: [ ] direct   [ ] marketplace-facilitated
Basis for that route determination: ____________________
```

**Validate:** the route is determined by how the sale is routed under HMRC's definition — **not** by the name of the platform. A confirming party and date are present.
**FAIL if:** the route is inferred from a platform name alone, or the confirming party is blank.

### 1.3 Border-charge owner and contract wording `[seller]`

```
Who bears charges arising at the border: ____________________
Exact wording stating this to the buyer: ____________________
Where published: ____________________
```

**Validate:** this is a **separate** field from 1.2 and separately populated. Do not assume a single delivery term covers every lane.
**FAIL if:** copied from 1.2 by default, or the buyer-facing wording is missing.

### 1.4 VAT number mechanism in declaration data `[fulfillment partner]`

```
How the VAT number is carried in declaration data: ____________________
Confirmed by: ____________________   Date: __________
```

**Validate:** the mechanism is confirmed by whoever prepares the declaration inputs, not assumed by the seller.

### 1.5 Declared-value source `[fulfillment partner]`

```
System of record supplying declared value: ____________________
Matches the source named in 1.1: [ ] yes  [ ] no
Confirmed by: ____________________   Date: __________
```

**FAIL if:** it does not match 1.1.

### 1.6 Returned shipment documents and data fields `[fulfillment partner]`

```
Documents returned after dispatch: ____________________
Data fields returned after dispatch: ____________________
Where they are stored: ____________________
Confirmed by: ____________________   Date: __________
```

**Validate:** list the returned set field by field. A partial return is an open exception.

### 1.7 VAT-return step after refunding an order with charged VAT `[seller]` + `[tax adviser]`

```
Step taken on the VAT return when an order with charged VAT is refunded: ____________________
Who performs it: ____________________   When: ____________________
Confirmed by: ____________________   Date: __________
```

**FAIL if:** no named step exists. Refunds happen; the step cannot be improvised.

### 1.8 Duty-reform policy review date `[seller]`

```
Review date: __________   Review owner: ____________________
```

**Validate:** the date is in the future and has an assigned owner. This row schedules a review — it does not record a conclusion.

---

## Record 2 — Published delivery promise

Wording published before purchase can become part of the contract. Store the wording buyers actually saw, verbatim and versioned. **Do not enter a universal transit time.**

### 2.1 Exact published delivery wording `[seller]`

```
Verbatim published wording (handover): ____________________
Verbatim published wording (transit): ____________________
Live from: __________   Live until: __________
Surfaces carrying it (list every page/template): ____________________
```

**Validate:** stored verbatim, not paraphrased; covers **both** handover and transit; every listed surface renders the same version.
**FAIL if:** surfaces disagree, or the stored text is an internal target rather than the published string.
**On change:** create a new version. Never edit in place — the historical string is the record.

---

## Record 3 — Disclosed return and remedy path

Two paths with different triggers. **Do not merge them.**

### 3.1 Cancellation return address (change of mind) `[seller]`

```
Return address: ____________________
Where disclosed to the buyer: ____________________
```

### 3.2 Direct return-cost owner, as disclosed (change of mind) `[seller]`

```
Who bears the direct cost of returning the goods: ____________________
Exact disclosure wording: ____________________
Where disclosed: ____________________
```

**FAIL if:** the cost owner is left to inference rather than stated.

### 3.3 Faulty / misdescribed / non-conforming path `[seller]`

```
Repair path: ____________________
Replacement path: ____________________
Postage path: ____________________
Where disclosed: ____________________
```

**FAIL if:** this path is empty while 3.1–3.2 are filled, or a single policy paragraph is reused for both triggers.

---

## Cross-record checks

- [ ] Border-charge owner in 1.3 is consistent with the delivery wording in 2.1 and the return disclosures in 3.1–3.3.
- [ ] A refund arising from a Record 3 path triggers the step named in 1.7.
- [ ] Declared-value source (1.5) matches the consignment value source (1.1).
- [ ] Every destination in scope is England, Scotland, or Wales. Any Northern Ireland destination halts here and goes to separate review.

---

## Pre-launch gate

Do not open orders until all of these are true:

- [ ] All twelve rows above filled — no placeholders, no "TBC".
- [ ] Every row has a named owner from the three labels.
- [ ] Every `[tax adviser]` and `[fulfillment partner]` row carries a confirming party **and** a date.
- [ ] All four tax items are recorded separately: point-of-sale VAT, border charges, declaration data, duty-reform review.
- [ ] Delivery wording is stored verbatim and identical across every listed surface.
- [ ] Both return triggers are documented separately.
- [ ] All cross-record checks pass.
- [ ] No open exceptions.

**Open exceptions** (each needs an owner and a resolution date):

```
| Exception | Owner | Raised | Resolution date | Status |
|---|---|---|---|---|
|  |  |  |  |  |
```

---

## Change log

Log every record change without overwriting history.

```
| Date | Record / row | Old value | New value | Owner | Confirmed by | Reason |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |
```

---

## Division of responsibility

- **Seller** — owns published wording and all customer-facing records; owns this file.
- **Tax adviser** — confirms tax positions on the seller's own facts.
- **Fulfillment partner** — confirms declaration inputs, declared-value source, and the shipment records returned after dispatch.

A fulfillment partner may execute agreed picking, packing, consolidation, carrier handover, and shipment-record return. A partner of this kind does not act as importer of record, register a seller for UK VAT, file with HMRC, certify product compliance, or provide tax or legal advice.

Source: [ASG Dropshipping's three-record model](https://asgdropshipping.com/china-fulfillment-uk-vat-delivery-returns/)
