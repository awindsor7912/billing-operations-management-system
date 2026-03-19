# System Architecture & Logic Model

## 🏗️ Layered Architecture
[cite_start]BOMS is designed following a modular "Separation of Concerns" principle across five distinct layers: [cite: 639, 646, 649]

1. [cite_start]**Intake Layer:** Converts unstructured email and form submissions into structured, trackable operational data[cite: 515, 569, 570].
2. [cite_start]**Processing & Routing Layer:** Acts as the state engine, governing item movement through the billing lifecycle using column-driven logic[cite: 516, 584, 585].
3. [cite_start]**Data Enrichment Layer:** Utilizes a dual-source data fusion pattern to merge intake metadata with structured enterprise reports[cite: 517, 593, 594].
4. [cite_start]**Compliance & Maintenance Layer:** Employs scheduled background automation for daily record reconciliation and lifecycle archival[cite: 518, 595, 609].
5. [cite_start]**Reporting & Visibility Layer:** An analytics layer built on the structured operational data to provide real-time transparency[cite: 521, 623].

## ⚙️ Core Innovation: Configuration-Driven Routing (v2.0)
[cite_start]A major architectural upgrade transitioned the system from "brittle" hard-coded conditional logic to a **Configuration-Driven Routing Model**[cite: 15, 20, 259]:
* [cite_start]**Dynamic Assignments:** Routing is determined by a centralized configuration repository rather than embedded code[cite: 259, 264].
* [cite_start]**Decoupled Logic:** System administrators can update role assignments directly within a configuration list without modifying automation flows[cite: 34, 266, 331].
* [cite_start]**Scalability:** Reduces maintenance complexity and eliminates risks associated with hard-coded user references during personnel changes[cite: 34, 268, 336, 345].

## 🔄 End-to-End Lifecycle
1. [cite_start]**Trigger:** Event intake via shared communication channels [cite: 539, 561-563].
2. [cite_start]**Parsing:** Metadata extraction and primary queue item creation[cite: 172, 173, 626].
3. [cite_start]**Enrichment:** Automated population of financial and status data via semantic model matching[cite: 174, 591, 592, 627].
4. [cite_start]**Assignment:** Logic-based routing to the assigned specialist[cite: 175, 574, 628].
5. [cite_start]**Transition:** Upon completion, the "Invoiced" flag triggers a state change to the processing phase[cite: 177, 178, 581, 631].
6. [cite_start]**Archival:** Records move to a read-only archive view before automated deletion at 60 days[cite: 179, 180, 632, 633].
