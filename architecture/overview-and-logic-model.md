# System Architecture & Logic Model

## 🏗️ Layered Architecture
BOMS is designed following a modular "Separation of Concerns" principle across five distinct layers: 

1. **Intake Layer:** Converts unstructured email and form submissions into structured, trackable operational data.
2. **Processing & Routing Layer:** Acts as the state engine, governing item movement through the billing lifecycle using column-driven logic.
3. **Data Enrichment Layer:** Utilizes a dual-source data fusion pattern to merge intake metadata with structured enterprise reports.
4. **Compliance & Maintenance Layer:** Employs scheduled background automation for daily record reconciliation and lifecycle archival.
5. **Reporting & Visibility Layer:** An analytics layer built on the structured operational data to provide real-time transparency.

## ⚙️ Core Innovation: Configuration-Driven Routing (v2.0)
A major architectural upgrade transitioned the system from "brittle" hard-coded conditional logic to a **Configuration-Driven Routing Model**:
* **Dynamic Assignments:** Routing is determined by a centralized configuration repository rather than embedded code.
* **Decoupled Logic:** System administrators can update role assignments directly within a configuration list without modifying automation flows.
* **Scalability:** Reduces maintenance complexity and eliminates risks associated with hard-coded user references during personnel changes.

## 🔄 End-to-End Lifecycle
1. **Trigger:** Event intake via shared communication channels.
2. **Parsing:** Metadata extraction and primary queue item creation.
3. **Enrichment:** Automated population of financial and status data via semantic model matching.
4. **Assignment:** Logic-based routing to the assigned specialist.
5. **Transition:** Upon completion, the "Invoiced" flag triggers a state change to the processing phase.
6. **Archival:** Records move to a read-only archive view before automated deletion at 60 days from the SharePoint List. Original documents remain stored in document libraries for auditing and compliance monitoring.
