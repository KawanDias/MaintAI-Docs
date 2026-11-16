# 3. Objectives and scope

## 3.1 General objective

Build a platform that identifies scheduled maintenance orders potentially affected by material shortages and provides information early enough for responsible teams to assess alternatives.

## 3.2 Specific objectives

1. Receive equipment and maintenance-order information.
2. Identify the materials required by each order.
3. Check material availability in stock.
4. Account for reservations and materials already committed.
5. Check potential alternatives at other storage locations.
6. Consider supplier replenishment lead times.
7. Identify material shortages.
8. Assess equipment criticality and proximity to the maintenance date.
9. Classify risk using deterministic and explainable rules.
10. Generate early alerts.
11. Present recommendations for human evaluation.
12. Provide dashboards and indicators.
13. Record decisions and monitoring history.

## 3.3 MVP scope

### Required capabilities

- Equipment registration.
- Material registration.
- Storage-location and stock registration.
- Maintenance-order registration and consultation.
- Assignment of materials to maintenance orders.
- Tracking of required and available quantities.
- Reservation handling.
- Shortage identification.
- Rule-based risk classification.
- Alert generation.
- Recommendation generation.
- Human approval or rejection of recommendations.
- Operational dashboard.
- Decision history.
- Automated or reproducible tests.

## 3.4 Outside the initial scope

- Generative artificial intelligence.
- Complex machine learning.
- Physical equipment-failure prediction.
- Automatic integration with all SAP modules.
- Automatic purchasing execution.
- Automatic stock transfers.
- Automatic changes to SAP maintenance orders.
- Native mobile application.
- Real-time industrial sensor integration.

## 3.5 Potential later evolution

- Authorized integration with SAP ERP / SAP S/4HANA.
- Use of SAP HANA Cloud.
- Synchronization of corporate data.
- More advanced analytics, if a real need is identified.
- Expansion of operational indicators and capabilities.

## 3.6 Initial MVP completion criteria

1. Essential records can be created and consulted.
2. Maintenance orders, equipment, and materials are correctly associated.
3. Availability is calculated consistently, respecting reservations.
4. Shortages are correctly identified.
5. Alternative storage locations and lead times are considered when the data is available.
6. Risk classification is explainable.
7. Alerts provide enough information for assessment.
8. Recommendations are presented without automatic execution.
9. Approval or rejection and the corresponding history are recorded.
10. The dashboard displays the main indicators.
11. The defined tests for the main scenarios can be executed.

## 3.7 Outcome indicators

- Number of maintenance orders analyzed.
- Number of orders with insufficient materials.
- Number of early alerts.
- Average alert lead time.
- Number of recommendations approved.
- Number of pending issues resolved.
- Materials with the highest shortage incidence.
- Equipment with the greatest exposure to risk.

These indicators are measurements to be collected. No performance or savings result should be claimed before it is measured.
