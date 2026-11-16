# 12. Roadmap

## 12.1 Purpose

This roadmap organizes the planned development of MaintAI into phases. The sequence and estimates may change as requirements are refined and technical resources become available.

## 12.2 Development phases

### Phase 1 — Discovery and requirements

Activities:
- Document the problem.
- Define target users.
- Identify use cases.
- Define business rules.
- Establish acceptance criteria.
- Set the initial scope.

**Deliverable:** requirements document.

### Phase 2 — Architecture and modeling

Activities:
- Define the architecture.
- Identify entities.
- Create relationships.
- Plan APIs.
- Plan the project structure.

**Deliverable:** architecture and data-model diagrams.

### Phase 3 — Environment setup

Activities:
- Prepare the development environment.
- Configure Node.js and SAP CAP tooling.
- Create the initial repository structure.
- Configure version control.

**Deliverable:** development environment ready.

### Phase 4 — Database and data model

Activities:
- Create the CDS schema.
- Implement entities.
- Create relationships.
- Create simulated data.
- Test queries.
- Validate data integrity.

**Deliverable:** structured and populated local database.

### Phase 5 — Backend and services

Activities:
- Create CAP services.
- Create APIs.
- Implement query operations.
- Implement validations.
- Organize business rules.

**Deliverable:** functional backend.

### Phase 6 — Risk analysis engine

Activities:
- Identify scheduled orders.
- Retrieve required materials.
- Calculate availability.
- Identify shortages.
- Account for reservations.
- Consider storage locations.
- Consider lead times.
- Classify risks.
- Generate alerts.
- Generate recommendations.

**Deliverable:** functional and testable analysis engine.

### Phase 7 — User interface

Activities:
- Develop the interface with SAP Fiori / UI5.
- Create the dashboard.
- Create order screens.
- Create material screens.
- Create stock views.
- Create alerts.
- Create recommendations.
- Create decision history.

**Deliverable:** usable interface.

### Phase 8 — Component integration

Activities:
- Connect frontend and backend.
- Connect backend and database.
- Validate data flow.
- Test communication.
- Handle errors.

**Deliverable:** integrated application.

### Phase 9 — SAP integration

Activities:
- Study available APIs and integration mechanisms.
- Identify required data sources.
- Prepare authentication and authorization.
- Implement read access to information.
- Validate synchronization.
- Document limitations.

Integration with a real corporate SAP system depends on authorized access, an available environment, and enabled APIs.

**Deliverable:** demonstrable integration or integration prototype, depending on available resources.

### Phase 10 — Testing and validation

Activities:
- Unit tests.
- Integration tests.
- Risk-engine tests.
- Availability tests.
- Reservation tests.
- Multiple-storage-location tests.
- Supplier-delay tests.
- Recommendation tests.
- Interface tests.
- Simulated industrial scenarios.

**Deliverable:** test documentation and results.

### Phase 11 — Deployment

Activities:
- Prepare a deployment environment.
- Configure SAP HANA Cloud if selected and available.
- Adjust configurations.
- Prepare persistence.
- Publish the application when infrastructure is available.
- Validate execution.

**Deliverable:** deployed application or documented local demonstration, depending on available resources.

### Phase 12 — Documentation and portfolio

Activities:
- Create Portuguese and English READMEs.
- Document architecture.
- Document the data model.
- Document APIs.
- Document business rules.
- Add diagrams.
- Add screenshots.
- Create a demonstration.
- Record test results.
- Explain technical decisions.

**Deliverable:** organized project suitable for professional presentation on GitHub.

## 12.3 Estimated schedule

| Period | Main activity |
|---|---|
| Week 1 | Requirements and discovery |
| Week 2 | Architecture, modeling, and environment |
| Week 3 | Database and backend |
| Week 4 | Services and business rules |
| Week 5 | Risk analysis engine |
| Week 6 | Interface and dashboard |
| Week 7 | Component integration |
| Week 8 | Testing and adjustments |
| Week 9 | SAP integration and deployment |
| Week 10 | Documentation and presentation |

This is an initial estimate, not a delivery commitment. The sequence may be adjusted as the project evolves and resources become available.

## 12.4 Expected final deliverables

1. Complete source code.
2. Structured database.
3. Demonstration data.
4. SAP CAP backend.
5. Functional APIs.
6. Risk analysis engine.
7. SAP Fiori / UI5 interface.
8. Dashboard.
9. Alert system.
10. Recommendation system.
11. Decision history.
12. Tests.
13. Technical documentation.
14. Architecture and workflow diagrams.
15. Portuguese README.
16. English README.
17. Screenshots.
18. Functional demonstration.
19. Organized GitHub repository.
