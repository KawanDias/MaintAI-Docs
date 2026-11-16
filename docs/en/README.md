# MaintAI — Industrial Maintenance Intelligence

MaintAI is a SAP-complementary application designed to identify, in advance, risks that scheduled industrial maintenance may be delayed or compromised because required parts, materials, or components are unavailable.

The project proposes an analysis and decision-support layer for industrial teams. The first version is planned as an independent application using simulated data and a local database, with an architecture prepared for possible future integration with SAP ERP / SAP S/4HANA and SAP HANA Cloud.

> **Status:** project planned / in development. The capabilities, architecture, and integrations described here represent the current plan and must not be interpreted as already implemented.

**Language:** [Português (Brasil)](../pt-BR/README.md) · **English**

## Objective

Identify, before the scheduled date, maintenance orders that may be affected by material shortages. MaintAI is expected to correlate orders, equipment, materials, stock, reservations, storage locations, and replenishment lead times, then present risks, alerts, and recommendations for human evaluation.

MaintAI **does not replace SAP** and is not intended to predict physical equipment failures. Its focus is the analysis of material availability required to perform scheduled maintenance.

## Documentation

| Document | Description |
|---|---|
| [01 — Project overview](01-project-overview.md) | Project context, proposal, target users, and concepts |
| [02 — Problem statement](02-problem-statement.md) | Operational situation, example, and boundaries of the claims |
| [03 — Objectives and scope](03-objectives-and-scope.md) | Objectives, MVP, exclusions, and success criteria |
| [04 — Requirements](04-requirements.md) | Initial functional and non-functional requirements |
| [05 — Business rules](05-business-rules.md) | Availability, shortages, risk, and decisions |
| [06 — Use cases](06-use-cases.md) | Actors and operational workflows |
| [07 — System architecture](07-system-architecture.md) | Components, responsibilities, and planned technologies |
| [08 — Data model](08-data-model.md) | Planned entities and relationships |
| [09 — Risk analysis engine](09-risk-analysis-engine.md) | Analysis inputs, process, rules, and outputs |
| [10 — SAP integration strategy](10-sap-integration-strategy.md) | Gradual approach to possible future integration |
| [11 — Testing and validation](11-testing-and-validation.md) | Test strategy and scenarios |
| [12 — Roadmap](12-roadmap.md) | Planned phases and estimated schedule |
| [13 — Glossary](13-glossary.md) | Terms used in the project |
| [Diagrams](../diagrams/README.md) | Shared diagram index |

The documentation changelog is available at [`../CHANGELOG.md`](../CHANGELOG.md).

## Planned technologies

- **JavaScript and Node.js:** backend development.
- **SAP CAP:** service and API structure.
- **CDS:** data modeling and service definitions.
- **SQLite:** initial local development and testing database.
- **SAP Fiori / SAPUI5:** web interface.
- **SAP HANA Cloud:** database considered for a later stage.
- **SQL:** queries and data manipulation.
- **Git and GitHub:** version control and publication.
- **Python:** possible future use for advanced analysis if justified by a real need.

The planned primary development environment is Visual Studio Code.

## Project principles

1. Start with an independent application and simulated data.
2. Prioritize deterministic, transparent, and explainable rules in the MVP.
3. Do not count reserved materials as freely available.
4. Consider stock at different storage locations and replenishment lead times.
5. Keep recommendations subject to human approval.
6. Do not automatically execute purchases, transfers, or SAP changes.
7. Clearly identify fictitious data and simulation results.
8. Do not claim savings or productivity improvements without measured results.

## Demonstration scenario

An industrial pump, BP-04, is scheduled for maintenance in five days. The order requires three bearings, but only one unit is available. The initial shortage is two units. MaintAI should check reservations, other storage locations, and replenishment lead time, classify the risk, and present an alert with alternatives for the planner.

This scenario is **fictional** and is intended to demonstrate the expected workflow.

## Scope and limitations

The first version covers master data, maintenance orders, material assignments, availability calculations, reservations, shortage identification, rule-based risk classification, alerts, recommendations, human decisions, dashboards, and history.

The initial scope excludes generative AI, complex machine learning, physical equipment-failure prediction, automatic integration with all SAP modules, automatic purchasing or stock transfers, automatic changes to SAP orders, a native mobile app, and real-time sensor integration.

## SAP integration

Integration with SAP ERP / SAP S/4HANA and the use of SAP HANA Cloud are later-stage activities. They depend on an available environment, authorized access, enabled APIs, and defined authentication and synchronization mechanisms. The absence of these resources must not block the local prototype.

## Repository organization

This repository contains MaintAI documentation only. The application's source code should remain in its own repository. Portuguese and English documents are maintained separately, while shared diagrams are stored once.

```text
MaintAI-Documentation/
├── README.md
└── docs/
    ├── README.md
    ├── CHANGELOG.md
    ├── pt-BR/
    │   ├── README.md
    │   └── 01..13 documentation files
    ├── en/
    │   ├── README.md
    │   └── 01..13 documentation files
    └── diagrams/
        └── README.md
```

## Industrial context notice

The project is framed around industrial companies, particularly the pulp and paper sector, as a possible application context. This does not confirm that any specific company has the problem described. MaintAI must be presented as a proposed solution for a plausible operational need, not as a response to a verified internal failure at any organization.

## Contributions and evolution

This is an initial specification. Entities, rules, architecture, and requirements may be refined during discovery, implementation, and validation. Relevant changes should be recorded in the changelog.

**Idioma / Language:** [Português (Brasil)](../pt-BR/README.md) · English
