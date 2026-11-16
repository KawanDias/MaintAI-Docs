# 1. Project overview

## 1.1 Identification

| Field | Description |
|---|---|
| Name | MaintAI — Industrial Maintenance Intelligence |
| Category | Industrial maintenance intelligence and decision-support system |
| Project responsibility | Analyst Engineer & Lead Developer |
| Development environment | Visual Studio Code |
| Status | Planned / in development |

## 1.2 Description

MaintAI is a SAP-complementary application intended to identify, in advance, risks that scheduled maintenance may be delayed or compromised because the parts, materials, and components required to perform the work are unavailable.

The application is expected to correlate maintenance orders, equipment, materials, stock, reservations, storage locations, and suppliers. Based on this analysis, it will identify potential shortages, classify risks, and present alerts and recommendations to the people responsible for the process.

MaintAI is not intended to replace SAP. Its purpose is to provide an additional operational intelligence and analysis layer to support decisions made by industrial teams.

## 1.3 Development context

The application will initially be built as an independent system, using simulated data and a local database. Its architecture should allow future integration with SAP ERP / SAP S/4HANA and SAP HANA Cloud.

This approach makes it possible to develop and validate the main workflow without requiring access to a corporate SAP environment from the beginning.

## 1.4 Main objective

Identify scheduled maintenance orders that may be affected by material shortages early enough for the responsible teams to assess alternatives.

The analysis workflow is expected to:
1. Receive equipment and maintenance-order information.
2. Identify the materials and quantities required by each order.
3. Check material availability in stock.
4. Account for reservations and materials already committed elsewhere.
5. Check potential availability at other storage locations.
6. Consider supplier replenishment lead times.
7. Identify shortages.
8. Assess equipment criticality and how close the maintenance date is.
9. Classify execution risk.
10. Generate alerts and recommendations.
11. Record decisions and provide monitoring indicators.

## 1.5 Target users

- Maintenance planners.
- Warehouse and storeroom personnel.
- Purchasing and supply professionals.
- Maintenance supervisors.
- Industrial managers.

Each group may use the information provided by the system to identify pending issues and support decisions related to material availability.

## 1.6 Planned capabilities

### Equipment management
Maintain equipment code, name or description, industrial area, location, category, criticality, and operational status.

### Material management
Maintain material code, description, category, unit of measure, available stock, reserved stock, minimum stock when applicable, associated supplier, and replenishment lead time.

### Stock and storage-location management
Track physical, reserved, available, committed, and potentially transferable quantities across storage locations.

### Maintenance-order management
Consult scheduled orders, their equipment, dates, priorities, statuses, and required materials.

### Risk analysis
Correlate order requirements with material availability, reservations, other storage locations, replenishment lead times, equipment criticality, and order priority.

### Alerts and recommendations
Present shortages and potential impacts, together with alternatives for human evaluation. The system is not expected to execute purchases or stock transfers automatically.

### Dashboard and history
Provide operational indicators and a record of decisions and follow-up actions.

## 1.7 Initial technology direction

- **JavaScript and Node.js:** backend development.
- **SAP CAP:** service and API structure.
- **CDS:** data modeling and service definitions.
- **SQLite:** initial local development and test database.
- **SAP Fiori / SAPUI5:** web interface.
- **SAP HANA Cloud:** database planned for a later stage.
- **SQL:** queries and data manipulation.
- **Git and GitHub:** version control and publication.
- **Python:** possible future use for advanced analysis if a real need is identified.

Visual Studio Code is the planned primary development environment.

## 1.8 Project principles

1. Start with an independent application and simulated data.
2. Prioritize deterministic, transparent, and explainable rules in the MVP.
3. Do not count reserved materials as freely available.
4. Consider stock across different storage locations and replenishment lead times.
5. Keep recommendations subject to human approval.
6. Do not automatically execute purchases, transfers, or SAP changes.
7. Clearly identify fictitious data and simulation results.
8. Do not claim savings or productivity improvements without measured results.

## 1.9 Demonstration scenario

An industrial pump, BP-04, is scheduled for maintenance in five days. The order requires three bearings, but only one unit is available. The initial shortage is two units. MaintAI is expected to check reservations, other storage locations, and replenishment lead time, classify the risk, and present an alert with alternatives for the planner.

This scenario is **fictional** and is intended to demonstrate the expected workflow.

## 1.10 Scope and limitations

The first version covers master data, maintenance orders, material assignments, availability calculations, reservations, shortage identification, rule-based risk classification, alerts, recommendations, human decisions, dashboards, and history.

The initial scope does not include generative AI, complex machine learning, physical equipment-failure prediction, automatic integration with every SAP module, automatic purchasing or stock transfers, automatic changes to SAP orders, a native mobile app, or real-time sensor integration.

## 1.11 SAP integration

Integration with SAP ERP / SAP S/4HANA and the use of SAP HANA Cloud are later-stage activities. They depend on an available environment, authorized access, enabled APIs, and defined authentication and synchronization mechanisms. The lack of these resources must not prevent development of the local prototype.

## 1.12 Repository organization

This repository contains MaintAI documentation only. The application's source code should remain in its own repository. Portuguese and English documents are maintained in separate folders, while shared diagrams are kept in `docs/diagrams/`.

## 1.13 Industrial context notice

The project is framed around industrial companies, particularly the pulp and paper sector, as a possible application context. This does not confirm that any specific company has the problem described. MaintAI must be presented as a proposed solution to a plausible operational need, not as a response to a verified internal failure at any organization.

## 1.14 Contributions and evolution

This documentation is an initial specification. Entities, rules, architecture, and requirements may be refined during discovery, implementation, and validation. Relevant changes should be recorded in the changelog.
