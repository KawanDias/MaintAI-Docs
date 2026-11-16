# 2. Problem statement

## 2.1 Operational context

Industrial equipment requires preventive and corrective maintenance. To perform scheduled maintenance as planned, the necessary parts, materials, and components must be available in the required quantities and at the right time.

An operational issue can occur when a scheduled maintenance order exists but the materials required to execute it are not sufficiently available.

## 2.2 Core problem

A material shortage may remain unnoticed until the maintenance date approaches. If the issue is identified too late, the team may have limited time to locate stock elsewhere, arrange replenishment, or reassess the maintenance plan.

MaintAI is intended to identify this type of situation before the scheduled date so that the responsible people can evaluate alternatives.

## 2.3 Illustrative example

- Equipment: industrial pump BP-04.
- Scheduled maintenance: in five days.
- Required material: industrial bearing.
- Required quantity: three units.
- Available stock: one unit.
- Initial shortage: two units.

The supplier's replenishment lead time and possible stock at other storage locations may affect whether the shortage can be resolved before the maintenance date.

This example is illustrative and does not represent a real operational record.

## 2.4 Potential consequences and alternatives

Depending on the actual situation, the responsible team may need to:
- Check whether the material is available at another storage location.
- Assess a transfer between storage locations.
- Request or expedite a purchase.
- Contact the supplier to confirm the delivery lead time.
- Reassess the maintenance schedule.

MaintAI should present relevant information and possible alternatives. Decisions and execution remain with the responsible people and processes.

## 2.5 Need for early analysis

The value of the proposed application is to correlate maintenance demand and material availability before the scheduled work date. The earlier a shortage is identified, the more time the team may have to assess alternatives. The system should therefore consider the maintenance date, current availability, reservations, other storage locations, and replenishment lead times whenever those data are available.

## 2.6 Industrial context

The project is contextualized for industrial companies, especially the pulp and paper sector, and considers that a solution of this type could be applicable to companies in that segment. There is no confirmation that Klabin or any other specific company has the exact problem described. The project must be presented as a proposed solution for a plausible operational need, not as a proven internal issue at a named company.

## 2.7 Problem statement

Industrial maintenance teams need an earlier and clearer view of whether the materials required by scheduled maintenance orders are likely to be available on time. Relevant information may be distributed across orders, equipment, inventory, reservations, storage locations, and supplier lead times. MaintAI proposes to consolidate and analyze these data to identify potential material shortages, communicate the associated risk, and support human decision-making.

## 2.8 Outside the problem definition

The project does not aim to predict physical equipment failures, replace an ERP system, autonomously purchase materials, or automatically transfer stock. Its focus is the risk to scheduled maintenance execution arising from the availability of required materials.
