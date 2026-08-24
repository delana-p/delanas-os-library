# Architecture

## Design Objective

The E-Commerce Financial Operations System creates a controlled path from fragmented commerce activity to supported accounting records and reviewer-ready close evidence.

It is designed around one central rule: **the accounting path follows the economic substance of the channel**.

## System Layers

| Layer | Responsibility | Representative inputs or outputs |
|---|---|---|
| Source | Preserve source-of-truth activity | Orders, invoices, settlements, remittances, 3PL movements, bank activity |
| Validation | Confirm completeness and required fields | Control totals, file periods, unique identifiers, missing records |
| Normalization | Standardize channel-specific structures | Channel, transaction type, settlement ID, customer, SKU, location |
| Routing | Select the correct accounting path | Settlement, AR, inventory, COGS, fulfillment, tax |
| Reconciliation | Calculate supported balances and differences | Expected cash, actual cash, open AR, uncleared balance, inventory rollforward |
| Exception | Isolate unsupported or failed activity | Variances, duplicates, missing evidence, unmapped items, cutoff issues |
| Human review | Apply judgment and approve material actions | Write-offs, deductions, manual entries, mappings, inventory adjustments |
| Accounting | Update or support QBO activity | Posting batches, cash application, clearing, adjustments |
| Evidence | Preserve close support and traceability | Rollforwards, exception log, approvals, tie-outs, audit trail |

## Responsibility Boundaries

### Deterministic processing

Used for calculations that should produce the same answer from the same inputs, including control totals, gross-to-net calculations, settlement matching, AR rollforwards, inventory equations, and variance quantification.

### Automation orchestration

Used to schedule intake, validate availability, route channel data, invoke controlled calculations, stop failed payloads, and deliver review packages.

### AI-assisted review

Used to classify exceptions, identify patterns, suggest likely matches, summarize unresolved items, and recommend next actions. AI assistance does not replace approval for material accounting judgment.

### Human judgment

Required for write-offs, unsupported deductions, policy changes, unusual classifications, material journal entries, inventory write-downs, and unresolved material differences.

### QuickBooks Online

Serves as the controlled accounting destination and reconciliation layer—not as a substitute for channel-level operational detail.

## Traceability Standard

Every material amount should be traceable through:

1. Source record
2. Normalized record
3. Applied accounting rule
4. Reconciliation result
5. Exception or approval, when applicable
6. QBO posting or balance
7. Reviewer-facing close evidence

