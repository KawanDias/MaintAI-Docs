# 6. Use cases

## 6.1 Actors

- Maintenance planner.
- Warehouse / storeroom professional.
- Purchasing / supply professional.
- Maintenance supervisor.
- Industrial manager.

## 6.2 UC-01 — Consult equipment

1. The user opens the equipment area.
2. The system displays available records.
3. The user reviews code, description, location, industrial area, criticality, and status.

## 6.3 UC-02 — Consult materials and stock

1. The user selects a material.
2. The system displays the associated storage locations.
3. The system shows physical, reserved, and available quantities.
4. The user assesses the material situation.

## 6.4 UC-03 — Consult maintenance orders

1. The user opens the order list.
2. The system displays order number, equipment, type, date, priority, and status.
3. The user selects an order.
4. The system displays the associated materials and quantities.

## 6.5 UC-04 — Run risk analysis

1. The system identifies scheduled orders.
2. It retrieves the materials required by each order.
3. It checks stock availability.
4. It accounts for reservations and commitments without duplicate deductions.
5. It checks other storage locations.
6. It considers available replenishment lead-time information.
7. It assesses equipment criticality and order priority.
8. It identifies shortages.
9. It classifies risk using deterministic rules.
10. It records the situation and generates alerts when applicable.

## 6.6 UC-05 — Consult an alert

1. The user opens the alerts area.
2. The user selects an alert.
3. The system displays the order, equipment, date, material, quantities, shortage, available replenishment information, criticality, and risk level.
4. The user reviews the information.

## 6.7 UC-06 — Evaluate a recommendation

1. The user opens an alert and its recommendations.
2. The user selects a recommendation.
3. The user evaluates the alternative.
4. The user approves or rejects the recommendation.
5. The user provides a justification when applicable.
6. The system records the decision, responsible person, and date.
7. The history and follow-up information are updated.

## 6.8 UC-07 — Monitor the dashboard

1. The user opens the dashboard.
2. The system displays indicators.
3. The user reviews orders with insufficient materials, active alerts, critical equipment, recurring material shortages, and pending recommendations.
4. The user drills down into details as needed.

## 6.9 UC-08 — Consult decision history

1. The user opens the history area.
2. The system displays available records.
3. The user reviews the related alert, responsible person, decision, justification, and date.

## 6.10 End-to-end demonstration flow

1. A maintenance order is received or registered.
2. MaintAI identifies the equipment and scheduled date.
3. It identifies required materials and quantities.
4. It checks stock and reservations.
5. It checks potential quantities at other storage locations.
6. It considers replenishment lead time.
7. It identifies any shortage.
8. It classifies the situation as a risk according to the defined rules.
9. It generates an alert and recommendations.
10. The planner evaluates the alternatives.
11. The decision is forwarded to the responsible area or recorded as pending.
12. The system updates history and indicators.

## 6.11 Notes

These use cases describe planned behavior. They do not imply that the corresponding screens, services, or integrations have already been implemented. Detailed permissions, exception flows, and validation messages remain subject to refinement.
