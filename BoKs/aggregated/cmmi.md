# CMMI: Capability Maturity Model Integration (aggregated)

**Source BoK:** CMMI Model v2.0 (2018), v2.2 (2022), v3.0 (2023), owned by the CMMI Institute (ISACA).
**Why aggregated:** since v2.0 the model is sold only through CMMI Institute's online viewer. The older **CMMI for Development v1.3 (2010)** was published by the SEI as a free technical report and is still the best free full text; this file uses it as the free backbone and maps it onto v2/v3.
**Gov tie:** G3, strongly. CMMI grew out of the SEI's Software CMM (1987–1993), funded by DoD after its 1980s software crisis. DoD and other agencies used maturity level ratings in source selection for decades, and many defense and federal IT contracts still ask for ML3.

## 1. Lineage

| Year | Model | Notes |
|---|---|---|
| 1987–1993 | SW-CMM (Humphrey, SEI) | Five maturity levels; key process areas. |
| 2002 / 2006 | CMMI v1.1 / v1.2 | Integrated software, systems, IPPD, supplier sourcing. |
| 2010 | **CMMI-DEV / -SVC / -ACQ v1.3** | Free SEI tech reports: [CMU/SEI-2010-TR-033 (DEV)](https://insights.sei.cmu.edu/library/cmmi-for-development-version-13/), [TR-034 (SVC)](https://insights.sei.cmu.edu/library/cmmi-for-services-version-13/), [TR-032 (ACQ)](https://insights.sei.cmu.edu/library/cmmi-for-acquisition-version-13/). |
| 2018 | CMMI v2.0 | Practice areas, practice groups, views; performance focus. CMMI Institute (ISACA). |
| 2023 | CMMI v3.0 | Adds safety, security, data, virtual work, people management domains. |

## 2. Maturity and capability levels

| Level | Maturity (organization, staged) | Meaning |
|---|---|---|
| 0 | (capability only) Incomplete | |
| 1 | Initial | Ad hoc; success depends on heroics. |
| 2 | Managed | Projects planned, performed, measured, controlled. |
| 3 | Defined | Organization-wide standard processes, tailored per project. |
| 4 | Quantitatively Managed | Statistical/quantitative objectives for quality and process performance. |
| 5 | Optimizing | Continuous improvement based on quantitative understanding. |

Capability levels (0–3) apply per practice area in the continuous representation.

## 3. v1.3 CMMI-DEV process areas (free full text)

22 process areas, by maturity level and category.

| PA | Name | ML | Category |
|---|---|---|---|
| REQM | Requirements Management | 2 | Project Mgmt (v1.3: Engineering) |
| PP | Project Planning | 2 | Project Mgmt |
| PMC | Project Monitoring and Control | 2 | Project Mgmt |
| SAM | Supplier Agreement Management | 2 | Project Mgmt |
| MA | Measurement and Analysis | 2 | Support |
| PPQA | Process and Product Quality Assurance | 2 | Support |
| CM | Configuration Management | 2 | Support |
| RD | Requirements Development | 3 | Engineering |
| TS | Technical Solution | 3 | Engineering |
| PI | Product Integration | 3 | Engineering |
| VER | Verification | 3 | Engineering |
| VAL | Validation | 3 | Engineering |
| OPF | Organizational Process Focus | 3 | Process Mgmt |
| OPD | Organizational Process Definition | 3 | Process Mgmt |
| OT | Organizational Training | 3 | Process Mgmt |
| IPM | Integrated Project Management | 3 | Project Mgmt |
| RSKM | Risk Management | 3 | Project Mgmt |
| DAR | Decision Analysis and Resolution | 3 | Support |
| OPP | Organizational Process Performance | 4 | Process Mgmt |
| QPM | Quantitative Project Management | 4 | Project Mgmt |
| OPM | Organizational Performance Management | 5 | Process Mgmt |
| CAR | Causal Analysis and Resolution | 5 | Support |

Each PA has **specific goals (SG)** and **specific practices (SP)**, plus **generic goals (GG)** and **generic practices (GP)** that institutionalize it (e.g. GP 2.1 Establish an Organizational Policy, GP 2.2 Plan the Process, … GP 3.1 Establish a Defined Process).

## 4. v2.0 / v3.0 structure

**Categories → capability areas → practice areas → practice groups (levels) → practices.**

The table below is assembled from CMMI Institute's public summaries. The exact practice area set differs a little between v2.0, v2.2 and v3.0 and by view, so check the licensed model viewer before relying on a specific name.

| Category | Capability area | Practice areas (abbr.) |
|---|---|---|
| **Doing** | Ensuring Quality | Requirements Development & Management (RDM), Process Quality Assurance (PQA), Verification & Validation (VV), Peer Reviews (PR) |
| | Engineering & Developing Products | Technical Solution (TS), Product Integration (PI) |
| | Delivering & Managing Services | Service Delivery Mgmt (SDM), Strategic Service Mgmt (STSM) |
| | Selecting & Managing Suppliers | Supplier Agreement Mgmt (SAM), Supplier Source Selection (SSS), Agreement Mgmt (AM), Technical Solution for acquisition (ATM) |
| | Ensuring Safety (v3) | Safety Mgmt |
| | Ensuring Security (v3) | Enabling Security (ESEC), Managing Security Threats & Vulnerabilities (MST) |
| **Managing** | Planning & Managing Work | Estimating (EST), Planning (PLAN), Monitor & Control (MC) |
| | Managing Business Resilience | Risk & Opportunity Mgmt (RSK), Incident Resolution & Prevention (IRP), Continuity (CONT) |
| | Managing the Workforce | Organizational Training (OT), Workforce Empowerment, People Mgmt (v3) |
| **Enabling** | Supporting Implementation | Causal Analysis & Resolution (CAR), Decision Analysis & Resolution (DAR) |
| | Managing Configurations / Data (v3) | Configuration Mgmt (CM), Data Quality, Data Management |
| **Improving** | Sustaining Habit & Persistence | Governance (GOV), Implementation Infrastructure (II) |
| | Improving Performance | Process Mgmt (PCM), Process Asset Development (PAD), Managing Performance & Measurement (MPM) |

The v2+ change most worth knowing: **Governance** and **Implementation Infrastructure** replace v1.3's generic practices, and **MPM** makes business-performance objectives central.

**Views:** model content is packaged into views such as Development, Services, Supplier Management, People, Safety, Security, Data, Virtual.

## 5. Appraisals

- **SCAMPI** (v1.3) → **Benchmark** and **Sustainment** appraisals (v2+). Ratings are valid for 3 years (sustainment can extend).
- Results are published in the CMMI Institute's [Published Appraisal Results (PARS)](https://cmmiinstitute.com/pars), which acquisition offices check.

## 6. Best free sources

| Need | Source |
|---|---|
| Full PA text (v1.3) | SEI reports linked in §1 |
| CMMI in agile settings | [SEI: CMMI or Agile: Why Not Embrace Both!](https://insights.sei.cmu.edu/library/cmmi-or-agile-why-not-embrace-both/) |
| Measurement (MA / MPM) | [Practical Software and Systems Measurement (PSM)](https://www.psmsc.com/) (DoD/Army-sponsored, free guides) |
| Process improvement | [SEI library](https://insights.sei.cmu.edu/library/); [NIST/SEMATECH e-Handbook](https://www.itl.nist.gov/div898/handbook/) for SPC at ML4/5 |

## 7. Crosswalk

| CMMI | Related |
|---|---|
| Engineering PAs (RD, TS, PI, VER, VAL) | ISO/IEC/IEEE 12207 & 15288 technical processes (see [life cycle file](iso-iec-ieee-12207-and-15288-life-cycle-processes.md)); SWEBOK KAs |
| PP, PMC, RSKM, IPM | PMBOK (see [pmbok.md](pmbok.md)) |
| CM | MIL-HDBK-61B; ITIL Service Configuration Mgmt; NIST 800-53 CM family |
| ESEC / MST (v3) | NIST SSDF (SP 800-218); 800-53 SA, RA, SI families |
| Service PAs | ITIL 4 (see [itil-4.md](itil-4.md)) |
| Whole model | ISO/IEC 33001 series (process assessment); SPICE |
