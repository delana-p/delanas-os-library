# Synthetic Close Package — Example Structure

This example shows the structure of a reviewer-ready e-commerce close package. It intentionally contains no client information, production thresholds, proprietary calculation logic, or executable implementation details.

## 1. Source Completeness

| Control | Example status | Evidence |
|---|---|---|
| Required channel files received | Complete | Source-file register |
| Reporting periods validated | Complete | Period-control report |
| Duplicate file and record review | Complete | Ingestion-control log |
| Source totals retained | Complete | Control-total schedule |

## 2. Channel Reconciliations

| Channel type | Primary reconciliation | Illustrative outcome |
|---|---|---|
| DTC | Gross activity to expected settlement, payout, bank, and clearing | Supported |
| Marketplace | Platform activity to marketplace settlement and bank | Supported with timing item |
| Wholesale/retail | Invoice to remittance, deductions, cash, and remaining AR | Open deduction exception |
| 3PL inventory | Beginning inventory plus movement to ending inventory and QBO | Supported after approved adjustment |

## 3. Rollforwards

- Settlement-in-transit by channel
- Clearing-account balance by channel
- Open AR and unapplied cash
- Retailer deduction and chargeback register
- Inventory by location or category
- Approved adjustment schedule

## 4. Exception Register

Each exception records:

- Unique reference
- Source and channel
- Accounting period
- Exception category
- Amount or quantity affected
- Available evidence
- Materiality and aging
- Recommended next action
- Assigned reviewer
- Resolution and approval reference

## 5. Human Approvals

Approval evidence is retained for material write-offs, deductions, credit memos, journal entries, mapping changes, inventory adjustments, unusual classification, and policy decisions.

## 6. Final Tie-Out

The close package separately identifies:

- Supported reconciled balance
- Supported timing or uncleared balance
- Approved adjustment
- Remaining unexplained variance
- Open exceptions carried forward

An unexplained variance is never relabeled as a supported timing difference merely to force the close to zero.

