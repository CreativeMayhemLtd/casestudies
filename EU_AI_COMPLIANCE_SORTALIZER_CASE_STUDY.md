# Case Study: Architectural Implementation of EU AI Act Compliance

## Project: Sortalizer Transparency & Compliance Hub
**Author:** Christopher Neitzert  
**Date:** December 2025  
**Scope:** Article 50 (Transparency) and Annex IV (Technical Documentation)

### Executive Summary
Most organizations are currently treating the EU AI Act as a documentation exercise. This case study details the architectural approach taken for Sortalizer, a Limited Risk AI system, to move compliance from a legal policy into the functional codebase. The objective was to address regulatory requirements—specifically transparency and traceability—through system design rather than administrative oversight.

---

### 1. The Problem: The Policy-First Fallacy
In 30 years of navigating multi-governance IT and security environments, I have observed a recurring failure: the belief that a policy PDF can mitigate a technical reality. For the EU AI Act, simply stating that a system utilizes AI is insufficient for the 2025 Code of Practice. 

**Standard deficiencies in current enterprise approaches:**
* Non-interoperable disclosures that rely on UI text alone.
* Lack of machine-readable metadata for downstream users and automated regulators.
* A disconnect between the Annex IV technical description and the actual live system state.

---

### 2. The Solution: Compliance-as-Architecture
To mitigate liability and ensure audit readiness, compliance was built into the Sortalizer stack across three primary vectors:

#### A. Article 50: Machine-Readable Transparency
Instead of a simple UI disclaimer, we implemented automated tagging for all synthetic outputs.
* **Mechanism:** Every AI-generated estimate, title, and description includes the `data-ai-generated="true"` attribute.
* **Result:** This ensures content is detectable by automated regulatory tools and web scrapers, fulfilling the December 2025 Marking and Labeling requirements.

#### B. JSON-LD System Provenance
For interoperability under the EU Data Act and AI Act, we developed a dynamic provenance schema.
* **Implementation:** A `provenance.json` export using JSON-LD.
* **Technical Detail:** Every output includes source links via the `isBasedOn` property. This enables full reconstruction of the data origin and the specific AI model configuration used at the time of generation.

#### C. Annex IV Technical Documentation
The AI Act requires a detailed technical description of the system. We translated complex regulatory requirements into a simplified technical description that remains audit-ready.
* **Scope:** Real-time documentation of AI providers, data sources, and system configuration.
* **Accessibility:** Hosted within a centralized Transparency & Compliance Hub for instantaneous regulatory access.

---

### 3. Key Technical Components

| Component | Regulatory Driver | Implementation |
| :--- | :--- | :--- |
| **Output Tagging** | Article 50(1) | `data-ai-generated="true"` attribute |
| **Metadata Schema** | EU Data Act / AI Act | JSON-LD / Schema.org integration |
| **Infrastructure** | GDPR / Sovereignty | EU-based (Hetzner Online GmbH, Germany) |
| **Audit Trail** | Annex IV | Automated system state logging and technical description |

---

### 4. Conclusion
The implementation at Sortalizer demonstrates that EU AI Act compliance is an engineering challenge that can be solved with the correct architectural mindset. By treating transparency as a data attribute rather than a legal disclosure, we have created a system that is resilient against future regulatory updates and audit requirements.

---

### Advisory
I provide architectural advisory for organizations transitioning from regulatory theory to operational reality. 

**Contact:** [mailto:info@creativemayhem.ltd]
