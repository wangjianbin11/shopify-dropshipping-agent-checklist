# Landed Cost Assumption Register

A working register for separating quoted facts from assumptions when an ecommerce team compares sourcing and fulfillment routes. Use one row per cost component and one version per scenario.

## Scenario identity

| Field | Value |
|---|---|
| Scenario ID |  |
| Product / SKU |  |
| Origin |  |
| Destination |  |
| Incoterm or commercial basis |  |
| Quantity / parcel profile |  |
| Currency and FX date |  |
| Prepared by / date |  |

## Cost components

| Component | Amount | Currency | Per unit / order / shipment | Source | Quote date | Valid until | Assumption? | Owner |
|---|---:|---|---|---|---|---|---|---|
| Product cost |  |  |  |  |  |  |  |  |
| Packaging / inserts / labels |  |  |  |  |  |  |  |  |
| Domestic transport |  |  |  |  |  |  |  |  |
| QC / handling / pick and pack |  |  |  |  |  |  |  |  |
| International freight |  |  |  |  |  |  |  |  |
| Fuel / remote / peak surcharge |  |  |  |  |  |  |  |  |
| Duty / tax estimate |  |  |  |  |  |  |  |  |
| Customs / brokerage / filing |  |  |  |  |  |  |  |  |
| Returns / reship reserve |  |  |  |  |  |  |  |  |
| Payment / FX cost |  |  |  |  |  |  |  |  |

## Reconciliation

| Order / shipment | Scenario version | Estimated landed cost | Actual landed cost | Variance | Variance reason | Corrective action |
|---|---|---:|---:|---:|---|---|
|  |  |  |  |  |  |  |

## Release gate

- [ ] Every non-zero component has a source or is marked as an assumption.
- [ ] Quote validity and currency are recorded.
- [ ] Product classification and declared-value questions are assigned to a qualified owner.
- [ ] The route model does not silently assume that tax, duty, brokerage, or remote fees are zero.
- [ ] Actual costs are reconciled back to the scenario after shipment.
- [ ] A material variance changes the next scenario version rather than being hidden in margin.

## Limits

This register is a planning and reconciliation tool, not customs, tax, or legal advice. Classification, valuation, origin, importer responsibilities, and destination rules require route-specific verification.

Source framework: https://asgdropshipping.com/research/landed-cost-trade-compliance-guide/
