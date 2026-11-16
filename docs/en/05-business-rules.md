# 5. Business rules

## 5.1 Purpose

These rules define the initial logic for assessing whether the materials required by a scheduled maintenance order are available. The rules are intended to be transparent, reproducible, and explainable.

## 5.2 Material availability

### Concepts

- **Physical quantity:** quantity recorded as physically held in stock.
- **Reserved quantity:** portion assigned to one or more identified requirements.
- **Committed quantity:** portion associated with other requirements that has not yet been deducted in the calculation.
- **Available quantity:** portion that may be considered for use after applicable deductions.

An initial calculation is:

```text
Available quantity = physical quantity - reserved quantity - committed quantity not yet deducted
```

The implementation must define how each reservation and commitment type is accounted for so that the same quantity is not deducted twice.

## 5.3 Shortage calculation

```text
Shortage = required quantity - available quantity for the order
```

- If the result is greater than zero, a material shortage exists.
- If the result is zero, the available quantity exactly meets the requirement.
- If the result is less than zero, availability exceeds the required quantity.

The calculation must use the quantity available for the specific order, not simply the physical stock figure.

## 5.4 Reservations and commitments

Reserved or committed quantities must not be treated as freely available for another order. The implementation must establish which commitments have already been deducted from stock balances to prevent duplicate deductions.

## 5.5 Multiple storage locations

The analysis may identify stock at other storage locations as a possible alternative. Such stock must be shown separately from the availability at the order's current location. A possible transfer is a recommendation for evaluation; MaintAI does not execute a transfer automatically in the initial scope.

## 5.6 Replenishment lead time

When supplier lead-time and date information are available, the system should compare the estimated replenishment date with the scheduled maintenance date. If replenishment is expected after the required date, that information should contribute to the risk assessment and be visible in the alert.

## 5.7 Equipment criticality and order priority

The risk assessment should consider:
- Equipment criticality.
- Maintenance-order priority.
- Scheduled maintenance date.
- Material shortage.
- Availability at other storage locations.
- Replenishment lead time.
- Existence of alternatives.

The precise weights, thresholds, and combination rules remain to be defined.

## 5.8 Risk classification

The initial version should use a classification that is:
- Deterministic.
- Based on explicit business rules.
- Explainable to the user.
- Reproducible in tests.
- Grounded in the data available for the analysis.

The project does not require artificial intelligence or machine learning for the first version.

## 5.9 Alerts

Where available, an alert should include:
- Equipment.
- Maintenance order.
- Scheduled date.
- Short material.
- Required quantity.
- Available quantity.
- Missing quantity.
- Estimated replenishment lead time or date.
- Equipment criticality.
- Risk level.
- Recommendations.

## 5.10 Recommendations and human approval

Possible recommendations include:
- Check availability at other storage locations.
- Assess a material transfer.
- Request or expedite a purchase.
- Contact the supplier.
- Reassess the maintenance schedule.

Recommendations are suggestions only. A responsible user must evaluate and approve or reject them. MaintAI must not automatically purchase materials, transfer stock, or modify SAP orders in the initial scope.

## 5.11 Functional boundary

MaintAI identifies risks related to material availability and scheduled maintenance execution. It does not claim to predict physical equipment failures and does not replace the ERP or the operational authority of the responsible teams.
