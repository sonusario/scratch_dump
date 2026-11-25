# COBIT 2019 (aggregated)

**Source BoK:** COBIT 2019 Framework: Introduction & Methodology, and Governance & Management Objectives, ISACA (2018). ISACA has released updates in its online "COBIT" toolkit since.
**Why aggregated:** the core books are free to ISACA members and paid for everyone else. The free federal equivalents (GAO Green Book, FISCAM) cover internal control and IT audit but not a full IT governance objective set.
**Gov tie:** G3. Federal IT auditors (IGs, GAO contractors) and SOX/financial-statement IT audits use COBIT as a reference; GAO's FISCAM and the Green Book are the federal-native analogues. CISA (the ISACA cert) is a DoD 8140 qualification for audit roles.

## 1. Principles

**Governance system principles (6):**
1. Provide stakeholder value
2. Holistic approach
3. Dynamic governance system
4. Governance distinct from management
5. Tailored to enterprise needs
6. End-to-end governance system

**Governance framework principles (3):** based on a conceptual model; open and flexible; aligned to major standards.

## 2. Components of a governance system (7)

Processes; Organizational structures; Principles, policies and frameworks; Information; Culture, ethics and behaviour; People, skills and competencies; Services, infrastructure and applications.

## 3. The 40 governance and management objectives

### Governance: EDM (Evaluate, Direct and Monitor)
- EDM01 Ensured governance framework setting and maintenance
- EDM02 Ensured benefits delivery
- EDM03 Ensured risk optimization
- EDM04 Ensured resource optimization
- EDM05 Ensured stakeholder engagement

### Management: APO (Align, Plan and Organize)
- APO01 Managed I&T management framework
- APO02 Managed strategy
- APO03 Managed enterprise architecture
- APO04 Managed innovation
- APO05 Managed portfolio
- APO06 Managed budget and costs
- APO07 Managed human resources
- APO08 Managed relationships
- APO09 Managed service agreements
- APO10 Managed vendors
- APO11 Managed quality
- APO12 Managed risk
- APO13 Managed security
- APO14 Managed data

### Management: BAI (Build, Acquire and Implement)
- BAI01 Managed programs
- BAI02 Managed requirements definition
- BAI03 Managed solutions identification and build
- BAI04 Managed availability and capacity
- BAI05 Managed organizational change
- BAI06 Managed IT changes
- BAI07 Managed IT change acceptance and transitioning
- BAI08 Managed knowledge
- BAI09 Managed assets
- BAI10 Managed configuration
- BAI11 Managed projects

### Management: DSS (Deliver, Service and Support)
- DSS01 Managed operations
- DSS02 Managed service requests and incidents
- DSS03 Managed problems
- DSS04 Managed continuity
- DSS05 Managed security services
- DSS06 Managed business process controls

### Management: MEA (Monitor, Evaluate and Assess)
- MEA01 Managed performance and conformance monitoring
- MEA02 Managed system of internal control
- MEA03 Managed compliance with external requirements
- MEA04 Managed assurance

## 4. Design factors and goals cascade

**11 design factors** used to tailor the governance system: enterprise strategy, enterprise goals, risk profile, I&T-related issues, threat landscape, compliance requirements, role of IT, sourcing model, IT implementation methods, technology adoption strategy, enterprise size.

**Goals cascade:** stakeholder drivers and needs → 13 enterprise goals (balanced-scorecard dimensions: financial, customer, internal, growth) → 13 alignment goals → governance & management objectives.

## 5. Performance management

Capability levels 0–5 per process (CMMI-based since 2019), and maturity levels for focus areas.

## 6. Free federal sources that cover the same ground

| COBIT domain | Free federal analogue |
|---|---|
| EDM, MEA02 (internal control) | [GAO Green Book (2025)](https://www.gao.gov/products/gao-25-107721); [OMB Circular A-123](https://www.whitehouse.gov/omb/information-resources/guidance/) |
| MEA04 (assurance), IT audit | [GAO FISCAM](https://www.gao.gov/fiscam); [GAO Yellow Book](https://www.gao.gov/yellowbook) |
| APO02/05/06 (strategy, portfolio, budget) | [OMB Circular A-11 / Capital Planning & Investment Control (CPIC)](https://www.whitehouse.gov/omb/information-resources/guidance/); [FITARA](https://www.cio.gov/) and the [IT Dashboard](https://itdashboard.gov/) |
| APO03 (EA) | [FEAF-II](https://obamawhitehouse.archives.gov/sites/default/files/omb/assets/egov_docs/fea_v2.pdf) |
| APO12/APO13/DSS05 (risk, security) | NIST RMF (SP 800-37), CSF 2.0, SP 800-53 |
| APO14 (data) | Federal Data Strategy; see [dama-dmbok.md](dama-dmbok.md) |
| BAI (build/acquire) | DoD AAF; ISO/IEC/IEEE 12207 (see [life cycle file](iso-iec-ieee-12207-and-15288-life-cycle-processes.md)) |
| DSS (operations) | ITIL (see [itil-4.md](itil-4.md)); NIST SP 800-34, 800-61 |

## 7. Crosswalk

- **COSO 2013** (internal control): 5 components, 17 principles, reproduced for government in the Green Book.
- **ISO/IEC 38500** (governance of IT): 6 principles; Evaluate–Direct–Monitor model that COBIT's EDM domain is named after.
- **NIST CSF 2.0 Govern (GV) function** overlaps EDM and APO12/13.
