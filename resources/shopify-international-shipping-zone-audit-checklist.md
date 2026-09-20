# Shopify International Shipping Zone Audit Checklist

A blank, per-country worksheet for auditing one destination at a time across the separate Shopify systems that decide whether a country can be bought from, whether its shipping rate is accurate, and whether its duties are actually collected.

**Status:** Template. It ships blank by design. Fill it in from your own admin and operating records.
**For:** Shopify operators, fulfillment leads, and operations contractors running international destinations, especially stores fulfilled from China.
**Not for:** Tax, customs, or legal determinations. See [Scope and limits](#scope-and-limits).

## Why this is a checklist and not an article

Three different Shopify systems decide what happens to one destination country. They live on different settings screens, and two of the three can be wrong without producing a single error at checkout:

| System | What it decides | Does it announce a failure? |
|---|---|---|
| Market and shipping zone coverage | Whether the country can be selected and checked out at all | **Yes**: the customer is blocked or the country is missing |
| Rate input versus carrier billing basis | Whether the shipping amount collected matches the shipping amount billed | **No**: the order completes at the wrong price |
| Duties configuration | Whether configured duties are actually charged | **No**: the order completes without collecting them |

Because two of the three are silent, they require a deliberate, per-country review. This file provides that review.

Method source and full reasoning: <https://asgdropshipping.com/shopify-shipping-zones-rates-china-fulfillment/>

## How to use

1. Use one row per country. Do not audit "Europe" or "Rest of world" as a single unit.
2. Start with the countries that carry revenue. Review the top three first, then add one new destination per cycle.
3. Run the columns in order. Column A gates everything after it. If a country cannot reach checkout, later rate and duty checks are not yet observable.
4. Record evidence, not impressions. Every `PASS` needs evidence that another person can recheck.
5. End every row with a decision, a named owner, and a recheck date.
6. Re-run affected rows after any new market, carrier, bulky SKU, or platform migration notice.

Copy the worksheet into your own tracker, or fork this repository and keep completed copies private. Do not commit real store data into a public fork.

## Worksheet

One row per destination country. All cells are blank on purpose.

| # | Destination country | A. Market active | B. In zone with available rate | C. Rate type in use | D. Rate input vs. carrier billing basis | E. Volumetric exposure checked | F. DDP or DAP deliberate? | G. Out of Rest of world zone | H. Duties prerequisites complete | I. Checkout promise defensible | J. Evidence reference | K. Owner | L. Decision | M. Recheck date |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 4 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 5 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 6 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 8 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 9 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| 10 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

## Column definitions

### A. Market active

**Meaning:** The destination country belongs to an active market in your store.

**Values:** `PASS`, `FAIL`, or `UNKNOWN`.

**Excludes:** This says nothing about whether a rate exists for the country. A country can be in an active market and still be unavailable at checkout.

### B. In zone with available rate

**Meaning:** The country sits inside a shipping zone that has at least one available shipping rate.

**Values:** `PASS`, `FAIL`, or `UNKNOWN`.

**Excludes:** This says nothing about whether the rate amount is correct. Availability and accuracy are separate checks.

A and B are both required. A customer can select a country at checkout only when it is included in both an active market and a shipping zone with an available rate.

### C. Rate type in use

**Meaning:** The rate configuration this destination's zone actually uses.

**Values:** `flat`, `price-based`, `weight-based`, `carrier-or-app-calculated`, `mixed`, or `UNKNOWN`.

**Excludes:** This is a configuration record, not a judgment. Column D holds the judgment.

### D. Rate input versus carrier billing basis

**Meaning:** Whether the rate input matches the basis the carrier actually bills on for the SKUs sent to this country.

**Values:** `ALIGNED`, `MISMATCH`, or `UNKNOWN`.

**Excludes:** This does not quantify the money at risk. It records only whether the inputs can diverge.

Shopify's weight-based rate uses product weight plus the store default package weight. Package dimensions are not an input for that rate type. Dimensions are an input for carrier-calculated rates. Carriers commonly bill on the greater of actual and volumetric weight, so a weight-based rate on a bulky, light SKU can create a silent structural mismatch.

### E. Volumetric exposure checked

**Meaning:** The carrier's published volumetric formula was applied to the outer carton of the bulkiest shipped SKUs, and the result was compared with the weight tier charged by the rate table.

**Values:** `CHECKED-NO-GAP`, `CHECKED-GAP-FOUND`, or `NOT-CHECKED`.

**Excludes:** This column does not store the gap amount or a divisor. Divisors vary by carrier and transport mode and must be confirmed with the carrier directly.

### F. DDP or DAP deliberate?

**Meaning:** Which operating choice applies to this country and whether it was selected deliberately rather than inherited as a default.

**Values:** `DDP-deliberate`, `DAP-deliberate`, `SET-BUT-UNINTENDED`, or `UNKNOWN`.

**Excludes:** This does not judge which choice is better. It records whether the choice was intentional.

Each country or region should have one deliberate operating choice. Choosing DAP on purpose is not a failure. The failure state is a mismatch between configured intent, checkout communication, and the actual operating flow.

### G. Out of Rest of world zone

**Meaning:** The country has its own applicable zone membership instead of relying only on the Rest of world catch-all.

**Values:** `PASS`, `FAIL`, or `UNKNOWN`.

**Excludes:** This is a prerequisite check, not proof that duties are calculated correctly.

### H. Duties prerequisites complete

**Meaning:** The documented setup prerequisites for collecting duties at checkout are satisfied for this country.

**Values:** `COMPLETE`, `INCOMPLETE`, `N/A-DAP`, or `UNKNOWN`.

Before recording `COMPLETE`, check each item:

- [ ] Carriers used for this destination support the intended duty-payment flow.
- [ ] The specific country is selected in the relevant duties settings.
- [ ] HS codes and country-of-origin information exist for the SKUs shipped there.
- [ ] Store policies and international sales notifications match what checkout charges.
- [ ] Required platform terms have been reviewed and the feature is actually active.
- [ ] Platform fees associated with duty-calculating orders are included in the landed-cost model.

**Excludes:** Completing these checks does not prove a duty amount is correct. It records setup completeness only.

### I. Checkout promise defensible

**Meaning:** The team can state a shipping price and delivery expectation for this country that it is prepared to support with written fulfillment and carrier inputs.

**Values:** `YES`, `NO`, or `UNKNOWN`.

**Excludes:** This is a commercial judgment, not a system reading. What the store charges is a shipping-rate question. When the parcel arrives is a fulfillment question. They can fail independently.

### J. Evidence reference

**Meaning:** A pointer to the artefact supporting the row's values.

**Format:** `<type>:<locator>:<date>`, such as `test-rates:zone-EU-standard:YYYY-MM-DD` or `order:reference:YYYY-MM-DD`.

**Excludes:** "I checked it" is not evidence.

### K. Owner

The named person accountable for the decision in column L. Use one name, not a team.

### L. Decision

**Values:** `FIX`, `EXCLUDE`, `ACCEPT-AS-IS`, or `PENDING`.

`PENDING` is not terminal. A row left pending past its recheck date remains an open finding.

### M. Recheck date

The date this row must be reviewed again regardless of the current outcome. It is required even for passing rows.

## Decision rules

Apply these rules in order. An earlier failure can make later findings unobservable.

1. **Coverage gates everything.** If A or B is `FAIL`, fix coverage before recording a pass in D through I.
2. **A mismatch in D is a finding.** Either price the tiers from the store's own billable-weight arithmetic or move the affected catalogue to a rate type that reads the required inputs.
3. **`NOT-CHECKED` is never `PASS`.** `UNKNOWN` and `NOT-CHECKED` are honest values, but they are not passing values.
4. **Deliberate DAP closes duties checks cleanly.** If F is `DAP-deliberate`, H may be `N/A-DAP` without making the row a duties failure. Customer-facing communication must still match the choice.
5. **Fix the loud failure first, then the silent ones.** Restore checkout eligibility before investigating problems that only appear after completed orders.
6. **Exclusion is a legitimate outcome.** If I is `NO` and cannot be made `YES` this cycle, exclude the destination until it can be priced and supported responsibly.
7. **Row closure requires four things.** Values in A through I, an evidence reference in J, a named owner in K, and both a decision and date in L and M.
8. **Platform migration does not suspend the audit.** Menu paths can change, but coverage, rate accuracy, duty handling, and delivery-promise checks still apply. Record the interface actually audited in J.

## Evidence requirements

A row is auditable only when another person can recheck its evidence.

| Columns | Accepted evidence |
|---|---|
| A, B | A dated rate-simulation result for that destination, or a dated capture of the market and zone state. A live test is stronger because a settings screen alone does not prove that separate systems agree. |
| C, D | A dated export or capture of the rate configuration for the zone containing that country. |
| E | The operator's own calculation sheet: measured carton dimensions, confirmed carrier formula and divisor, dated result, and comparison with the charged tier. |
| F, G, H | A dated capture of the configuration for that country, plus a completed order comparison when available. |
| I | A written, dated price-and-delivery statement approved by the owner. |

The following are not accepted evidence:

- An undated screenshot.
- A check on a neighbouring country generalized to this one.
- A settings page treated as proof of runtime behaviour without an order or simulation.
- A vendor or article example substituted for the operator's own measurement.
- A note that only says the reviewer checked it.

If a check cannot be run, record `UNKNOWN` and the reason in J. Never use `0`, `PASS`, or a blank to represent a check that was not performed.

## Scope and limits

- This is an operational configuration checklist. It is not tax, customs, or legal advice, and completing it does not establish that any duty setup is correct for a country.
- Duty amounts displayed at checkout can be estimates. Setup completeness and calculation correctness are separate.
- Carrier volumetric divisors vary by carrier and transport mode. Confirm the divisor directly with the carrier.
- The worksheet contains no sample rows or reference data. Any numbers in this file are field definitions, not observations.
- This resource contains no ASG shipment records, customer outcomes, savings figures, or performance data, and none should be inferred from it.
- Platform behaviour changes. Re-verify current platform documentation before relying on a configuration statement.

## Provenance

- **Resource:** `resources/shopify-international-shipping-zone-audit-checklist.md`
- **Author:** Janson, ASG Dropshipping
- **Created:** 2026-09-20
- **Revision:** 1.0.0
- **Method source:** Linked once above.
- **Corrections:** Open an issue in this repository. Platform-behaviour corrections should cite the current official documentation and the date it was read.
