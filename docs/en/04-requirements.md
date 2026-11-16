# 4. Requirements

## 4.1 Considerations

The requirements in this document are an initial specification based on the MaintAI project context. They describe planned behavior, not features that are already implemented. Details that have not yet been decided are explicitly left open.

## 4.2 Actors

- **Maintenance planner:** reviews scheduled orders, material shortages, alerts, and recommendations.
- **Warehouse / storeroom professional:** checks stock, reservations, and potential availability at other storage locations.
- **Purchasing / supply professional:** evaluates supplier lead times and replenishment alternatives.
- **Maintenance supervisor:** monitors risks and evaluates operational priorities.
- **Industrial manager:** follows indicators and the overall situation.

## 4.3 Functional requirements

| ID | Requirement |
|---|---|
| FR-001 | The system shall allow equipment records to be registered and consulted. |
| FR-002 | The system shall allow material records to be registered and consulted. |
| FR-003 | The system shall maintain stock information associated with storage locations. |
| FR-004 | The system shall allow maintenance orders to be registered and consulted. |
| FR-005 | The system shall associate each maintenance order with its equipment. |
| FR-006 | The system shall associate required materials and quantities with maintenance orders. |
| FR-007 | The system shall calculate material availability while accounting for applicable reservations and commitments. |
| FR-008 | The system shall identify a shortage when the quantity required exceeds the quantity available for the order. |
| FR-009 | The system shall consider potential material availability at other storage locations when data is available. |
| FR-010 | The system shall consider supplier replenishment lead times when data is available. |
| FR-011 | The system shall classify risk using explicit and explainable rules. |
| FR-012 | The system shall generate alerts for identified situations that may compromise scheduled maintenance. |
| FR-013 | The system shall present recommendations as alternatives for human evaluation. |
| FR-014 | The system shall allow a user to approve or reject a recommendation. |
| FR-015 | The system shall record decisions, responsible users, dates, and justifications when provided. |
| FR-016 | The system shall provide a dashboard with relevant operational indicators. |
| FR-017 | The system shall provide access to the history of alerts and decisions. |

## 4.4 Initial non-functional requirements

- **Clarity:** risk information, shortages, and recommendations should be understandable to the intended users.
- **Traceability:** the system should retain the information that explains an alert and the decisions made about it.
- **Consistency:** availability and shortage calculations should follow defined business rules.
- **Maintainability:** business rules and services should be organized so they can be evolved.
- **Testability:** the main calculations and workflows should support repeatable tests.
- **Security:** access control and authentication must be defined before use with real corporate data.
- **Extensibility:** the architecture should allow future integration with SAP systems without making that integration a prerequisite for the local MVP.
- **Data transparency:** simulated data and simulated results must be clearly identified.

Quantitative performance, availability, and security targets remain to be defined.

## 4.5 Initial acceptance rules

- Reserved materials must not be counted as freely available.
- The shortage must reflect the required quantity minus the availability considered for the order.
- The analysis should identify when estimated replenishment occurs after the required date, if the relevant dates are available.
- An alternative at another storage location must be presented as a possibility, not as an executed transfer.
- Recommendations must not execute actions automatically.
- Approvals and rejections must be recorded.
- Alerts must provide enough information for the responsible user to understand the source of the risk.

## 4.6 Dependencies and open decisions

- Final risk levels and classification thresholds.
- Policy for accounting for commitments and reservations without double deduction.
- Availability and transfer rules across storage locations.
- Data update format and frequency.
- Application roles, access profiles, and permissions.
- Quantitative performance and availability targets.
- Concrete APIs and mechanisms for any future SAP integration.
