# 11. Testing and validation

## 11.1 Purpose

Validate that MaintAI correctly handles the main records, availability calculations, shortage identification, risk classification, alerts, recommendations, and decision history.

## 11.2 Planned test types

### Unit tests
Validate individual calculations and business rules, especially availability and shortage calculations.

### Integration tests
Validate communication between services, the database, and the risk analysis engine.

### Risk-engine tests
Validate order processing, reservations, other storage locations, replenishment lead times, criticality, priority, and risk classification.

### Interface tests
Validate the display and consultation of orders, stock, alerts, recommendations, dashboards, and decision history.

### Scenario tests
Run end-to-end simulated industrial scenarios to verify that the system produces coherent results.

## 11.3 Essential scenarios

- Sufficient stock for all required materials.
- Insufficient stock for one or more materials.
- Reserved quantities that must not be treated as available.
- Commitments that have already been deducted, to prevent double deduction.
- Potential stock at another storage location.
- Replenishment expected before the maintenance date.
- Replenishment expected after the maintenance date.
- High equipment criticality or order priority.
- Recommendation approval and rejection.
- Missing supplier lead-time information.

## 11.4 Manual validation example

- Equipment: industrial pump BP-04.
- Maintenance: in five days.
- Material: industrial bearing.
- Required quantity: three units.
- Available quantity: one unit.

Expected initial shortage: two units, before considering any valid alternative stock or replenishment information. The final risk level depends on the rules defined for the implementation.

## 11.5 Alert validation

An alert should be checked for the presence and consistency of:
- Order and equipment.
- Scheduled date.
- Material.
- Required quantity.
- Available quantity.
- Missing quantity.
- Estimated replenishment lead time or date, when available.
- Criticality.
- Risk level.
- Recommendations.

## 11.6 Recommendation validation

- Recommendations are presented as alternatives.
- The user can approve or reject a recommendation.
- The decision is recorded.
- The system does not automatically execute purchases, transfers, or SAP changes.

## 11.7 Metrics and results

The project may collect:
- Orders analyzed.
- Orders with insufficient materials.
- Early alerts.
- Average alert lead time.
- Approved recommendations.
- Resolved pending issues.
- Materials with the highest shortage incidence.
- Equipment with the greatest risk exposure.

These are proposed indicators. Results must be measured before performance claims are made.

## 11.8 Test records

Each test record should include:
- Test identifier.
- Scenario and data used.
- Expected result.
- Actual result.
- Status (passed or failed).
- Notes and any defects found.

## 11.9 General validation criterion

The MVP should be considered validated when the essential workflows produce consistent, explainable, and repeatable results for the defined scenarios, and when the main test outcomes and limitations are documented.
