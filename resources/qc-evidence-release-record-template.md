# QC Evidence and Release Record Template

A blank, copyable record set for quality control evidence and release authorization on high-value ecommerce goods. Copy this file into your own repository or wiki, fill the tables with your data, and version it alongside your operating procedures.

Every table below is empty on purpose. Nothing here is a completed record, a customer case, or performance evidence from any operation.

## When to use it

Apply this to SKUs where **expected-loss exposure** is high — the cost of one bad unit reaching a customer across replacement, freight, dispute handling, and time spent reconstructing what happened. That is a per-SKU judgment about exposure, not a universal price threshold.

## The three layers

| Layer | Name | What it does |
|---|---|---|
| L1 | SKU-level Judgment Standard | Defines object, method, pass rule, fail rule, and required evidence form |
| L2 | Traceable Inspection Record | Records what was checked, by whom, when, against which spec version, with evidence |
| L3 | Release Control | Decides whether a failed unit may ship |

L1 and L2 establish evidence. L3 controls whether a failed unit ships. Building L1 and L2 without L3 produces good documentation of units that left anyway.

## 1. SKU control plan (L1)

| SKU | Spec version | Checkpoint | Object | Method | Pass rule | Fail rule | Evidence form required |
|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |

**Owner of this table:** ______________ **Last reviewed:** ______________

Write pass and fail rules so that two people reading them reach the same verdict; a rule that says the item looks acceptable is not a rule. Bump the spec version whenever any rule changes, and never edit a rule in place, because past records are only interpretable against the version in force when they were made.

## 2. Inspection record (L2)

| Record ID | SKU / Order / Unit | Inspector | Date & time | Station | Equipment / calibration | Spec version checked against | Result | Evidence files |
|---|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

**Owner of this table:** ______________

Each record must resolve to a SKU, batch, order, or unit — an identifier that leads back to a physical object. Keep original evidence files, not re-exports or screenshots of them, and keep the modification history of the record itself. Inspector is a person's name, not a shared login.

Photo or video selection is fact-specific. Images can fix appearance, labels, accessories, packed condition, and serial or date codes. Claims about motion or continuity may require video. Neither format guarantees any external outcome.

## 3. Exception and reinspection log

| Exception ID | Linked inspection record | Exception type | Isolation action taken | Escalation path | Reinspection ID | Reinspection result | Date |
|---|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |

**Owner of this table:** ______________

A reinspection creates a **new** record. Never overwrite the failed record — it is the part of the trail that carries information. Isolation is physical first, then reflected in system state so the two match.

## 4. Release authorization (L3)

| SKU / Order / Unit | Standard version | Inspection record ID (or reinspection ID) | Release decision | Release owner (name) | Date | Signature |
|---|---|---|---|---|---|---|
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |

**Owner of this table:** ______________

Release owner is a named, authorised person. A role, a team, or a system account cannot sign.

## Pre-release gate

Do not ship the unit until every line is checked:

- [ ] The unit resolves to a SKU, batch, order, or unit identifier
- [ ] A control plan version exists for this SKU and the checkpoint applied
- [ ] An inspection record exists and names the spec version it was checked against
- [ ] Original evidence files are attached and openable
- [ ] If the unit ever failed: it was physically isolated and system state was set to match
- [ ] If the unit ever failed: a separate reinspection record exists and the failed record is intact
- [ ] Release authorization is signed by a named authorised owner
- [ ] No open safety or regulatory question is attached to this unit or its stock

## Safety and regulatory path

If a potential safety or regulatory risk appears, it leaves this workflow entirely:

1. Stop sale.
2. Quarantine potentially affected stock.
3. Pause open orders.
4. Escalate to a qualified safety or compliance lead.

**A commercial release signature cannot override safety, regulatory, stop-sale, recall, or reporting duties.** Do not let a signed release form close a safety escalation.

## Retrieval test

Run this on a schedule, not once at setup. Pick a shipped unit at random and hand the identifier to someone who did not inspect it. Ask them to produce, unaided:

1. The control plan version in force at inspection time
2. The inspection record
3. The original evidence files
4. Any exception and reinspection record
5. The signed release authorization

If it requires searching chat threads or asking the original inspector, the records are not retrievable and the system is not yet working.

## Retention

Set retention against the longest applicable process your operation actually faces. No universal retention period follows from this template — decide it deliberately and write the figure into the change log below.

## Limits

A complete record helps reconstruct what happened and identify a unit. It does not decide how a payment platform, carrier, marketplace, or regulator will rule, and it guarantees no chargeback, return, carrier, marketplace, or regulatory outcome. These tables are tools only.

## Change log

| Version | Date | Change | Changed by | Approved by |
|---|---|---|---|---|
|  |  |  |  |  |
|  |  |  |  |  |

Source and provenance for the underlying QC framing: https://asgdropshipping.com/qc-proof-high-ticket-products-photo-video-checklist/
