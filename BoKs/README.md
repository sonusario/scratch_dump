# Bodies of Knowledge (BoKs)

An index of **freely available, comprehensive, well-organized bodies of knowledge**, starting with software engineering and expanding outward through systems engineering, security, management, data, and the government compliance machinery that ties them together.

Started 2026-11-25. Links were current as of that date; government sites move often (see the [link notes](#link-notes) at the bottom).

## How to read this index

Each entry has a short line on what it covers and two tags:

- **Access:** `Free` (download or read online, no account), `Free (reg.)` (free with a registration or click-through), `Paid` (the authoritative text costs money).
- **Gov:** how strongly it is tied to US government compliance.
  - `G1` mandated or directly cited by US law, regulation, OMB/DoD policy, or contracts (FISMA, FAR/DFARS, DoDI, FedRAMP, CMMC…).
  - `G2` produced by a US government body as guidance, or widely used as the de facto federal yardstick.
  - `G3` private/international, but it shaped or was shaped by US government practice (e.g. CMMI from DoD funding, ISO 27001 mapped into NIST 800-53).
  - `—` little government tie.

Where the authoritative text is `Paid` and the free derivatives are thin or scattered, there is a file in [`aggregated/`](aggregated/) that pulls the best free information into one well-organized outline. Those are marked **📘 aggregated**.

## Contents

1. [Software engineering](#1-software-engineering)
2. [Secure software development](#2-secure-software-development)
3. [Systems engineering and acquisition](#3-systems-engineering-and-acquisition)
4. [Cybersecurity and information assurance](#4-cybersecurity-and-information-assurance)
5. [Cybersecurity and IT workforce frameworks](#5-cybersecurity-and-it-workforce-frameworks)
6. [Risk, governance, audit and internal control](#6-risk-governance-audit-and-internal-control)
7. [Project, program and agile management](#7-project-program-and-agile-management)
8. [Business analysis and requirements](#8-business-analysis-and-requirements)
9. [IT service management and operations](#9-it-service-management-and-operations)
10. [Enterprise architecture](#10-enterprise-architecture)
11. [Data management, privacy and AI](#11-data-management-privacy-and-ai)
12. [Software testing and quality](#12-software-testing-and-quality)
13. [Safety-critical and regulated software](#13-safety-critical-and-regulated-software)
14. [Accessibility and digital service delivery](#14-accessibility-and-digital-service-delivery)
15. [Computing curricula (the academic BoKs)](#15-computing-curricula-the-academic-boks)
16. [Crosswalks: how the compliance BoKs map to each other](#16-crosswalks-how-the-compliance-boks-map-to-each-other)

---

## 1. Software engineering

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [SWEBOK Guide v4.0](https://www.computer.org/education/bodies-of-knowledge/software-engineering) (IEEE Computer Society, 2024) | The reference BoK for the discipline. 18 knowledge areas: requirements, architecture, design, construction, testing, operations, maintenance, configuration management, engineering management, process, models & methods, quality, security, professional practice, economics, computing / math / engineering foundations. Each KA cites the IEEE/ISO standards it rests on. [Topic list](https://computer.org/education/bodies-of-knowledge/software-engineering/topics). | Free (reg.) | G3 |
| [NASA Software Engineering Handbook (SWEHB, NASA-HDBK-2203)](https://swehb.nasa.gov/) | Requirement-by-requirement guidance for NPR 7150.2 (NASA's software engineering requirements), plus software assurance and safety (NASA-STD-8739.8). Probably the most complete free, government, *practical* software engineering handbook online: rationale, guidance, small-project notes, lessons learned, and templates for each requirement. | Free | G1 (NASA) |
| [DoD Software Modernization / Software Fast Track resources](https://dodcio.defense.gov/Library/) (DoD CIO library) | DoD Software Modernization Strategy, DevSecOps Fundamentals, software factory guidance, cATO material. Not one book but the policy shelf for DoD software. | Free | G1 (DoD) |
| [SEI Digital Library](https://insights.sei.cmu.edu/library/) (Carnegie Mellon SEI, an FFRDC funded by DoD) | Decades of technical reports on architecture (ATAM, Views & Beyond), acquisition, measurement, agile in government, secure coding. Searchable rather than structured as one BoK. | Free | G2 |
| [Guide to the Systems Engineering BoK's software chapters (SEBoK Part 6)](https://sebokwiki.org/wiki/Systems_Engineering_and_Software_Engineering) | How SE and SwE relate. See section 3. | Free | G3 |
| [ISO/IEC/IEEE 12207 software life cycle processes](aggregated/iso-iec-ieee-12207-and-15288-life-cycle-processes.md) | The process standard behind SWEBOK, DoD SE practice and CMMI. | Paid → **📘 aggregated** | G3 |
| [CMMI (Capability Maturity Model Integration)](aggregated/cmmi.md) | Process maturity model born from DoD's 1980s software crisis; still a source-selection criterion in DoD contracts. Now owned by ISACA. | Paid → **📘 aggregated** | G3 |

## 2. Secure software development

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [NIST SP 800-218 Secure Software Development Framework (SSDF) v1.1](https://csrc.nist.gov/pubs/sp/800/218/final) | Practices grouped as Prepare the Organization, Protect the Software, Produce Well-Secured Software, Respond to Vulnerabilities. Each practice references BSIMM, SAMM, ISO 27034, etc. The basis of the [CISA Secure Software Development Attestation Form](https://www.cisa.gov/secure-software-attestation-form) required of federal software suppliers under OMB M-22-18 / M-23-16. [SP 800-218A](https://csrc.nist.gov/pubs/sp/800/218/a/final) adds generative AI. | Free | G1 |
| [CISA Secure by Design](https://www.cisa.gov/securebydesign) | Principles and pledge for vendors: memory-safe languages, default-secure configuration, eliminating vulnerability classes. | Free | G2 |
| [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard/) | Testable requirements for web app security at three levels. Very well organized; often used as a contract requirement. | Free | G3 |
| [OWASP SAMM](https://owaspsamm.org/) | Software Assurance Maturity Model: governance, design, implementation, verification, operations. Referenced by the SSDF. | Free | G3 |
| [OWASP Web Security Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) | Complete web pentest methodology. | Free | — |
| [OWASP Top 10](https://owasp.org/www-project-top-ten/) and [Cheat Sheet Series](https://cheatsheetseries.owasp.org/) | Most common risk classes, and short how-to-do-it-right guides. | Free | G3 (cited by PCI DSS, DISA ASD STIG) |
| [MITRE CWE](https://cwe.mitre.org/) / [CAPEC](https://capec.mitre.org/) | Taxonomies of software weakness types and attack patterns. CISA/DHS-sponsored. CWE Top 25 published with CISA. | Free | G2 |
| [SEI CERT Coding Standards](https://wiki.sei.cmu.edu/confluence/display/seccode) | Rules and recommendations for C, C++, Java, Perl, Android. | Free | G2 |
| [DISA Application Security & Development STIG](https://public.cyber.mil/stigs/) | DoD checklist for applications (search "Application Security and Development"). | Free | G1 (DoD) |
| [DoD Enterprise DevSecOps Fundamentals & Reference Designs](https://dodcio.defense.gov/Portals/0/Documents/Library/DoD%20Enterprise%20DevSecOps%20Fundamentals%20v2.5.pdf) | DoD's model of a software factory: pipeline, activities and tools, CNCF Kubernetes and AWS reference designs, [activities & tools guidebook](https://dodcio.defense.gov/Portals/0/Documents/Library/DevSecOpsActivitesToolsGuidebook.pdf). | Free | G1 (DoD) |
| [BSIMM](https://www.blackduck.com/resources/analyst-reports/bsimm.html) | Descriptive survey of what real software security initiatives do (~125 activities). | Free (reg.) | G3 |

## 3. Systems engineering and acquisition

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [SEBoK: Guide to the Systems Engineering Body of Knowledge](https://sebokwiki.org/) (INCOSE, IEEE SMC, Stevens/SERC) | The SE counterpart of SWEBOK, as a wiki: foundations, life cycle models, SE management, product & service SE, enterprise SE, related disciplines (SwE, PM, industrial, safety, security). Updated about twice a year. | Free | G2 (SERC is a DoD UARC) |
| [NASA Systems Engineering Handbook (SP-2016-6105 Rev 2)](https://www.nasa.gov/reference/systems-engineering-handbook/) | Full SE engine from concept to disposal, with technical management processes. Plain-language and well organized. | Free | G1 (NASA) |
| [DoD Systems Engineering Guidebook (2022)](https://www.cto.mil/wp-content/uploads/2023/06/SE-Guidebook-2022.pdf) and [Engineering of Defense Systems Guidebook](https://www.cto.mil/wp-content/uploads/2024/10/Eng-Def-Sys-Change2-7October2024-v3.pdf) | DoD's implementation of DoDI 5000.88 engineering policy: technical reviews (SRR, PDR, CDR…), the 16 technical processes, SE Plan content. | Free | G1 (DoD) |
| [DoD Adaptive Acquisition Framework (AAF)](https://aaf.dau.edu/) (DAU) | The six acquisition pathways (Urgent Capability, Middle Tier, Major Capability, **Software Acquisition**, Defense Business Systems, Acquisition of Services) with policy, flowcharts and artifacts for each. | Free | G1 (DoD) |
| [DAU Acquipedia](https://www.dau.edu/acquipedia-home) and [DAU Glossary](https://www.dau.edu/glossary) | Encyclopedia of acquisition terms and practices: cost, contracting, logistics, test & evaluation, SE. | Free | G1 (DoD) |
| [NIST SP 800-160 Vol. 1 Rev. 1, Engineering Trustworthy Secure Systems](https://csrc.nist.gov/pubs/sp/800/160/v1/r1/final) | Systems security engineering laid over the ISO/IEC/IEEE 15288 process model. Each of the 30 life cycle processes gets security outcomes and activities. **The best free derivative of 15288.** [Vol. 2](https://csrc.nist.gov/pubs/sp/800/160/v2/r1/final) covers cyber resiliency. | Free | G1/G2 |
| [ISO/IEC/IEEE 15288 system life cycle processes](aggregated/iso-iec-ieee-12207-and-15288-life-cycle-processes.md) | The process standard behind INCOSE, SEBoK, NIST 800-160 and DoD SE. | Paid → **📘 aggregated** | G3 |
| [INCOSE SE Handbook](https://www.incose.org/publications/se-handbook) | Practitioner handbook keyed to 15288. Use SEBoK + NASA + DoD guidebooks as the free equivalent. | Paid (free to INCOSE members) | G3 |
| [Federal Acquisition Regulation (FAR)](https://www.acquisition.gov/browse/index/far) / [DFARS](https://www.acquisition.gov/dfars) | The rules every federal contract runs on; DFARS 252.204-7012 is what makes NIST 800-171 and CMMC binding. Note the ongoing [Revolutionary FAR Overhaul](https://www.acquisition.gov/far-overhaul) (2025-) rewriting parts. | Free | G1 |

## 4. Cybersecurity and information assurance

### 4a. The NIST/federal core (the "compliance spine")

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [NIST Cybersecurity Framework (CSF) 2.0](https://www.nist.gov/cyberframework) | Six functions (Govern, Identify, Protect, Detect, Respond, Recover), 22 categories, 106 subcategories, with informative references to 800-53, ISO 27001, CIS Controls. The common language between executives and engineers. | Free | G2 (G1 for critical infrastructure EOs) |
| [NIST SP 800-53 Rev. 5 Security & Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) + [800-53B baselines](https://csrc.nist.gov/pubs/sp/800/53/b/upd1/final) + [800-53A assessment](https://csrc.nist.gov/pubs/sp/800/53/a/r5/final) | 20 control families, ~1,000 controls and enhancements; Low/Moderate/High baselines; assessment procedures. Mandatory for federal systems under FISMA/FIPS 200. Browse it in the [SP 800-53 Cybersecurity and Privacy Reference Tool](https://csrc.nist.gov/projects/cprt/catalog#/cprt/framework/version/SP_800_53_5_1_1/home). | Free | G1 |
| [NIST SP 800-37 Rev. 2 Risk Management Framework (RMF)](https://csrc.nist.gov/pubs/sp/800/37/r2/final) | Prepare → Categorize → Select → Implement → Assess → Authorize → Monitor. How a federal system gets an Authority to Operate (ATO). Companion: [FIPS 199](https://csrc.nist.gov/pubs/fips/199/final), [FIPS 200](https://csrc.nist.gov/pubs/fips/200/final), [SP 800-60](https://csrc.nist.gov/pubs/sp/800/60/v1/r1/final), [SP 800-30](https://csrc.nist.gov/pubs/sp/800/30/r1/final), [SP 800-39](https://csrc.nist.gov/pubs/sp/800/39/final), [SP 800-137](https://csrc.nist.gov/pubs/sp/800/137/final). | Free | G1 |
| [NIST RMF online resource center](https://csrc.nist.gov/projects/risk-management) | Quick-start guides and FAQs per RMF step. | Free | G1 |
| [NIST SP 800-171 Rev. 3](https://csrc.nist.gov/pubs/sp/800/171/r3/final) + [800-171A](https://csrc.nist.gov/pubs/sp/800/171/a/r3/final) + [800-172](https://csrc.nist.gov/pubs/sp/800/172/final) | Protecting Controlled Unclassified Information (CUI) in non-federal systems (contractors, universities). | Free | G1 |
| [NIST Special Publications 800 series index](https://csrc.nist.gov/publications/sp800) | The whole library: incident response ([800-61r3](https://csrc.nist.gov/pubs/sp/800/61/r3/final)), digital identity ([800-63-4](https://pages.nist.gov/800-63-4/)), zero trust ([800-207](https://csrc.nist.gov/pubs/sp/800/207/final)), supply chain ([800-161r1](https://csrc.nist.gov/pubs/sp/800/161/r1/upd1/final)), contingency planning ([800-34](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final)), crypto key management ([800-57](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final)), config management ([800-128](https://csrc.nist.gov/pubs/sp/800/128/upd1/final)), log management ([800-92r1](https://csrc.nist.gov/pubs/sp/800/92/r1/ipd)). | Free | G1/G2 |
| [NIST OSCAL](https://pages.nist.gov/OSCAL/) | Machine-readable formats for catalogs, baselines, SSPs, assessment plans/results, POA&Ms. FedRAMP is moving to it. | Free | G1 |
| [NIST Glossary (CSRC)](https://csrc.nist.gov/glossary) | Every term defined across NIST pubs, with sources. | Free | G2 |
| [FISMA](https://www.cisa.gov/topics/cyber-threats-and-advisories/federal-information-security-modernization-act), [OMB Circular A-130](https://www.whitehouse.gov/wp-content/uploads/legacy_drupal_files/omb/circulars/A130/a130revised.pdf) | The law and the OMB policy that make the NIST documents mandatory for agencies. | Free | G1 |
| [CNSSI 1253](https://www.cnss.gov/) | 800-53 baselines for National Security Systems (via CNSS). | Free | G1 (NSS) |

### 4b. Programs that apply the spine

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [FedRAMP](https://www.fedramp.gov/) ([documents & templates](https://www.fedramp.gov/documents-templates/), [FedRAMP 20x](https://www.fedramp.gov/20x/)) | Authorization of cloud services for federal use: 800-53 baselines + FedRAMP parameters, SSP templates, continuous monitoring. 20x moves to Key Security Indicators and automation. | Free | G1 |
| [CMMC 2.0](https://dodcio.defense.gov/CMMC/) ([resources & documentation](https://dodcio.defense.gov/CMMC/Resources-Documentation), [32 CFR Part 170](https://www.ecfr.gov/current/title-32/subtitle-A/chapter-I/subchapter-G/part-170)) | DoD contractor certification: Level 1 (FAR 52.204-21, 15 reqs), Level 2 (800-171 r2, 110 reqs), Level 3 (+ 800-172). Model overview, scoping guides, assessment guides. | Free | G1 (DoD) |
| [DoD RMF / DoDI 8510.01](https://www.esd.whs.mil/Portals/54/Documents/DD/issuances/dodi/851001p.pdf) and [RMF Knowledge Service](https://rmfks.osd.mil/) | DoD's implementation of RMF (RMF KS needs a CAC). | Free / CAC | G1 (DoD) |
| [DISA STIGs and SRGs](https://public.cyber.mil/stigs/) | Security Technical Implementation Guides: concrete configuration checklists per product, derived from 800-53 via CCIs. Viewable with STIG Viewer. | Free | G1 (DoD) |
| [DoD Zero Trust Strategy & Reference Architecture](https://dodcio.defense.gov/Library/) | 7 pillars, 152 activities, target vs advanced ZT. | Free | G1 (DoD) |
| [CISA Cross-Sector Cybersecurity Performance Goals](https://www.cisa.gov/cross-sector-cybersecurity-performance-goals) | A short prioritized subset of CSF practices for critical infrastructure. | Free | G2 |
| [CISA Known Exploited Vulnerabilities (KEV) catalog](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) | Vulnerabilities agencies must patch under BOD 22-01. | Free | G1 |
| [HIPAA Security Rule guidance (NIST SP 800-66r2)](https://csrc.nist.gov/pubs/sp/800/66/r2/final) | Health data security implemented with NIST controls. | Free | G1 (HHS) |
| [CJIS Security Policy](https://le.fbi.gov/cjis-division/cjis-security-policy-resource-center) | FBI policy for criminal justice information, now aligned to 800-53. | Free | G1 |
| [IRS Publication 1075](https://www.irs.gov/pub/irs-pdf/p1075.pdf) | Safeguards for federal tax information at agencies/contractors. | Free | G1 |

### 4c. General cybersecurity BoKs

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [CyBOK: Cyber Security Body of Knowledge v1.1](https://www.cybok.org/) (UK, NCSC-funded) | 21 knowledge areas in five groups: human/organizational/regulatory, attacks & defences, systems security, software & platform security, infrastructure security. The most rigorous free academic cybersecurity BoK. | Free | — (UK gov) |
| [MITRE ATT&CK](https://attack.mitre.org/) and [D3FEND](https://d3fend.mitre.org/) | Adversary tactics/techniques, and the matching defensive techniques (D3FEND is NSA-funded). | Free | G2 |
| [CIS Critical Security Controls v8.1](https://www.cisecurity.org/controls) and [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks) | 18 prioritized controls with implementation groups; hardening benchmarks per product. Mapped to CSF and 800-53. | Free (reg.) | G3 |
| [NSA Cybersecurity Advisories & Guidance](https://www.nsa.gov/Press-Room/Cybersecurity-Advisories-Guidance/) | Hardening and threat guidance, including Commercial Solutions for Classified (CSfC) and CNSA 2.0 (post-quantum). | Free | G2 |
| [ISO/IEC 27001 / 27002](aggregated/iso-iec-27001-27002.md) | The international ISMS and control catalog, mapped to 800-53 and CSF. | Paid → **📘 aggregated** | G3 |
| [(ISC)² CISSP CBK](aggregated/isc2-cissp-cbk.md) | The 8-domain CBK behind CISSP, a DoD 8140 qualification. | Paid → **📘 aggregated** | G1 via DoD 8140 |
| [CompTIA Security+ exam objectives (SY0-701)](https://www.comptia.org/certifications/security) | Five domains, the baseline DoD 8140 cert for many roles. The objectives PDF is free and is a good syllabus of entry-level security. | Free (reg.) | G1 via DoD 8140 |

## 5. Cybersecurity and IT workforce frameworks

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [NICE Workforce Framework for Cybersecurity (NIST SP 800-181r1)](https://www.nist.gov/itl/applied-cybersecurity/nice/nice-framework-resource-center) ([current components v2](https://www.nist.gov/itl/applied-cybersecurity/nice/nice-framework-resource-center/current-version)) | Work roles, competency areas, and Task/Knowledge/Skill statements (TKS). Effectively a BoK expressed as job content. | Free | G1/G2 |
| [DoD Cyber Workforce Framework (DCWF)](https://dodcio.defense.gov/Cyber-Workforce/DCWF) | DoD's extension of NICE: 70+ work roles including software engineering, data/AI and enablers, with KSATs. [DoD Manual 8140.03](https://www.esd.whs.mil/Portals/54/Documents/DD/issuances/dodm/814003p.PDF) sets qualification (education, training, certification) per role. | Free | G1 (DoD) |
| [CyberSeek career pathways](https://www.cyberseek.org/pathway.html) | NICE roles as career paths with job market data. | Free | G2 |
| [OPM classification standards (2210 IT Management)](https://www.opm.gov/policy-data-oversight/classification-qualifications/classifying-general-schedule-positions/) | Federal IT job series definitions. | Free | G1 |
| [SFIA 9 (Skills Framework for the Information Age)](https://sfia-online.org/en/sfia-9) | ~150 IT skills × 7 responsibility levels. Global, used by UK/AU/NZ governments. | Free (reg., non-commercial) | — |
| [ACM/IEEE Software Engineering Competency Model (SWECOM)](https://computer.org/volunteering/boards-and-committees/professional-educational-activities/software-engineering-competency-model) | Skills and activities per SWEBOK KA at five competency levels. | Free | G3 |

## 6. Risk, governance, audit and internal control

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [GAO Green Book: Standards for Internal Control in the Federal Government (2025 revision, GAO-25-107721)](https://www.gao.gov/products/gao-25-107721) | 5 components, 17 principles (adapted from COSO 2013) applied to federal agencies; required by OMB A-123 and the FMFIA. **The best free derivative of COSO.** | Free | G1 |
| [GAO Yellow Book: Government Auditing Standards (GAGAS 2024)](https://www.gao.gov/yellowbook) | Standards for audits of government entities and federal awards. | Free | G1 |
| [GAO FISCAM (Federal Information System Controls Audit Manual)](https://www.gao.gov/fiscam) | How auditors test IT controls (security management, access, segregation of duties, config management, contingency) in federal systems; mapped to 800-53. The free audit-side counterpart to COBIT. | Free | G1 |
| [OMB Circular A-123](https://www.whitehouse.gov/wp-content/uploads/legacy_drupal_files/omb/memoranda/2016/m-16-17.pdf) | Enterprise Risk Management and internal control for agencies. | Free | G1 |
| [NIST SP 800-30 / 800-39 / IR 8286 series](https://csrc.nist.gov/pubs/ir/8286/r1/final) | Risk assessment, organization-wide risk, and integrating cyber risk into ERM. Free derivative of ISO 31000-style ERM. | Free | G1/G2 |
| [COBIT 2019](aggregated/cobit.md) | ISACA governance framework for enterprise IT: 40 objectives, design factors, capability levels. | Paid / members → **📘 aggregated** | G3 |
| [COSO Internal Control / ERM frameworks](https://www.coso.org/) | Private-sector root of the Green Book and SOX 404 practice. Use the Green Book for free full text. | Paid | G3 |
| [Secure Controls Framework (SCF)](https://securecontrolsframework.com/) | Free meta-framework of ~1,300 controls crosswalked to 200+ laws, regulations and frameworks. | Free | G3 |

## 7. Project, program and agile management

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [PMBOK Guide](aggregated/pmbok.md) (PMI) | Principles, performance domains, and (in the Process Groups Practice Guide) the classic 49 processes. ANSI standard. | Paid (free PDF to PMI members) → **📘 aggregated** | G3 |
| [GAO Cost Estimating and Assessment Guide (GAO-20-195G)](https://www.gao.gov/products/gao-20-195g) | 12-step cost estimating process, best practices and audit criteria. | Free | G1 (audit criteria) |
| [GAO Schedule Assessment Guide (GAO-16-89G)](https://www.gao.gov/products/gao-16-89g) | 10 best practices for an integrated master schedule. | Free | G1 |
| [GAO Agile Assessment Guide (GAO-24-105506)](https://www.gao.gov/products/gao-24-105506) | Agile adoption, requirements, cost/schedule/EVM in agile, with assessment checklists. | Free | G1 |
| [GAO Technology Readiness Assessment Guide (GAO-20-48G)](https://www.gao.gov/products/gao-20-48g) | TRL-based evaluation of critical technologies. | Free | G1 |
| [EIA-748 Earned Value Management](https://www.dau.edu/acquipedia-article/earned-value-management-evm) via the [DoD EVMS Interpretation Guide](https://www.acq.osd.mil/asda/dpc/api/ipm/policy-guidance.html) | EIA-748 (32 guidelines) is paid; DoD's interpretation guide and DAU material explain all 32 for free. | Free (derivative) | G1 |
| [The Scrum Guide](https://scrumguides.org/) | The 13-page definition of Scrum. | Free | — |
| [SAFe (Scaled Agile Framework)](https://framework.scaledagile.com/) | Full framework articles online. Widely used in DoD software programs. | Free (web) | G3 |
| [Disciplined Agile](https://www.pmi.org/disciplined-agile) | PMI's toolkit of process choices. | Free (web, partial) | — |
| [PRINCE2](https://www.axelos.com/certifications/propath/prince2-project-management) | UK government project method. Paid; principles/themes/processes are summarized in the PMBOK aggregated file. | Paid | — (UK gov) |

## 8. Business analysis and requirements

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [BABOK Guide v3](aggregated/babok.md) (IIBA) | 6 knowledge areas, 30 tasks, 50 techniques, the BACCM core model. | Paid (free PDF to IIBA members) → **📘 aggregated** | — |
| [SWEBOK v4 Software Requirements KA](https://www.computer.org/education/bodies-of-knowledge/software-engineering) | Requirements engineering within SWEBOK. | Free (reg.) | G3 |
| [IREB CPRE Foundation syllabus & handbook](https://cpre.ireb.org/en/downloads-and-resources/downloads) | Requirements engineering BoK as syllabus + free handbook. | Free | — |
| [18F Guides (archived)](https://guides.18f.gov/) and [Digital.gov user research guides](https://digital.gov/topics/research/) | Federal product discovery, user research, agile requirements. 18F was closed in 2025; guides may only be available via archives. | Free | G2 |

## 9. IT service management and operations

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [ITIL 4](aggregated/itil-4.md) (PeopleCert/Axelos) | Service value system, 34 practices. Basis of most federal help desk and service contracts. | Paid → **📘 aggregated** | G3 |
| [FitSM](https://www.fitsm.eu/) | Free, lightweight ITSM standard (originally EU-funded): 14 processes with requirements, templates, and role models. A ready-made free derivative of ITIL / ISO 20000. | Free | — |
| [Google SRE books](https://sre.google/books/) | SRE, The SRE Workbook, Building Secure & Reliable Systems: all free online. | Free | — |
| [NIST SP 800-34 Contingency Planning](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final) / [SP 800-184 Cyber Event Recovery](https://csrc.nist.gov/pubs/sp/800/184/final) | Continuity and recovery for federal systems. | Free | G1 |
| [TBM Taxonomy](https://www.tbmcouncil.org/learn-tbm/tbm-taxonomy/) | Technology Business Management cost model; used in federal IT spending reports (OMB IT Dashboard). | Free (reg.) | G2 |

## 10. Enterprise architecture

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [Federal Enterprise Architecture Framework v2 (FEAF-II)](https://obamawhitehouse.archives.gov/sites/default/files/omb/assets/egov_docs/fea_v2.pdf) | OMB's architecture framework: six reference models (performance, business, data, application, infrastructure, security). | Free | G1 |
| [DoD Architecture Framework (DoDAF 2.02)](https://dodcio.defense.gov/Library/DoD-Architecture-Framework/) | Viewpoints and models for defense architectures; successor work moving to UAF. | Free | G1 (DoD) |
| [TOGAF Standard 10th ed.](https://www.opengroup.org/togaf) | ADM cycle and content framework. Free for personal/internal use with Open Group registration. | Free (reg.) | G3 |
| [Unified Architecture Framework (UAF, OMG)](https://www.omg.org/spec/UAF/) | Model-based successor to DoDAF/MODAF/NAF. | Free | G2 |
| [Federal Integrated Business Framework (FIBF)](https://ussm.gsa.gov/fibf/) | Standard federal business functions, capabilities and use cases for shared services. | Free | G1 |

## 11. Data management, privacy and AI

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [DAMA-DMBOK 2](aggregated/dama-dmbok.md) | 11 data management knowledge areas around governance. | Paid → **📘 aggregated** | G3 |
| [Federal Data Strategy](https://strategy.data.gov/) | 10 principles, 40 practices, and action plans for agency data. | Free | G1 |
| [Evidence Act / Chief Data Officer resources](https://www.cdo.gov/) | Required agency data governance under the Foundations for Evidence-Based Policymaking Act. | Free | G1 |
| [DoD Data Strategy (VAULTIS)](https://media.defense.gov/2020/Oct/08/2002514180/-1/-1/0/DOD-DATA-STRATEGY.PDF) | Visible, Accessible, Understandable, Linked, Trustworthy, Interoperable, Secure. | Free | G1 (DoD) |
| [NIST Privacy Framework 1.0](https://www.nist.gov/privacy-framework) | CSF-shaped framework for privacy risk (Identify-P, Govern-P, Control-P, Communicate-P, Protect-P). | Free | G2 |
| [Fair Information Practice Principles (FIPPs)](https://www.fpc.gov/resources/fipps/) and [Federal Privacy Council](https://www.fpc.gov/) | The root principles of the Privacy Act and OMB A-130 privacy requirements; PIAs, SORNs. | Free | G1 |
| [NIST AI Risk Management Framework (AI 100-1)](https://www.nist.gov/itl/ai-risk-management-framework) + [Playbook](https://airc.nist.gov/airmf-resources/playbook/) + [GenAI Profile (AI 600-1)](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence) | Govern, Map, Measure, Manage for AI systems. | Free | G2 (cited by OMB AI memos) |
| [DAMA Dictionary / NIST Big Data Interoperability Framework (SP 1500)](https://www.nist.gov/itl/big-data-nist) | Vocabulary and reference architecture for big data. | Free | G2 |

## 12. Software testing and quality

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [ISTQB syllabi](https://www.istqb.org/certifications/) | Foundation, advanced (test analyst, test manager, technical test analyst), and specialist syllabi (security, performance, automotive, AI testing). Free PDFs and a free glossary; together a well-organized testing BoK. | Free | — |
| [SWEBOK v4 Software Testing and Software Quality KAs](https://www.computer.org/education/bodies-of-knowledge/software-engineering) | Testing techniques, levels, and quality management. | Free (reg.) | G3 |
| [DoD Test & Evaluation Enterprise Guidebook / DAU T&E](https://www.dau.edu/acquipedia-article/test-and-evaluation-te) and [DOT&E guidance](https://www.dote.osd.mil/Guidance/) | Developmental and operational test policy for defense systems, including software and cybersecurity T&E (DoD Cybersecurity T&E Guidebook). | Free | G1 (DoD) |
| [NIST SP 800-115 Technical Guide to Information Security Testing](https://csrc.nist.gov/pubs/sp/800/115/final) | Security testing and assessment methods. | Free | G2 |
| [ISO 9001 / AS9100 quality management](https://www.iso.org/iso-9001-quality-management.html) | Paid. Free derivatives: [NASA Quality](https://sma.nasa.gov/sma-disciplines/quality) and the [Baldrige Excellence Framework](https://www.nist.gov/baldrige/publications/baldrige-excellence-framework) (NIST, free criteria; a US government quality program). | Paid / free derivatives | G2 (Baldrige) |

## 13. Safety-critical and regulated software

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [DO-178C airborne software](aggregated/do-178c.md) | FAA-recognized (AC 20-115D) objectives for airborne software assurance levels A–E. | Paid (RTCA) → **📘 aggregated** | G1 (FAA) |
| [FAA Software and Airborne Electronic Hardware](https://www.faa.gov/aircraft/air_cert/design_approvals/air_software) | FAA orders, ACs, job aids, and CAST position papers. | Free | G1 |
| [NASA Software Safety Guidebook / NASA-STD-8739.8](https://standards.nasa.gov/) | Software assurance and safety standard and guidance. | Free | G1 (NASA) |
| [MIL-STD-882E System Safety](https://quicksearch.dla.mil/) and the [Joint Software Systems Safety Engineering Handbook](https://www.acq.osd.mil/se/) | DoD system and software safety process (search "MIL-STD-882" on ASSIST QuickSearch). | Free | G1 (DoD) |
| [FDA medical device software guidance](https://www.fda.gov/medical-devices/digital-health-center-excellence/guidances-digital-health-content) | Software as a medical device, premarket cybersecurity, General Principles of Software Validation. | Free | G1 (FDA) |
| [FDA 21 CFR Part 11](https://www.ecfr.gov/current/title-21/chapter-I/subchapter-A/part-11) | Electronic records and signatures. | Free | G1 |

## 14. Accessibility and digital service delivery

| BoK | What it covers | Access | Gov |
|---|---|---|---|
| [Section508.gov](https://www.section508.gov/) and the [Revised 508 Standards](https://www.access-board.gov/ict/) | Federal ICT accessibility law, standards (incorporating WCAG 2.0 AA), testing methods (ICT Testing Baseline), and procurement guidance. | Free | G1 |
| [WCAG 2.2](https://www.w3.org/TR/WCAG22/) and [Understanding / Techniques](https://www.w3.org/WAI/standards-guidelines/wcag/) | The W3C accessibility guidelines; also the basis of the 2024 DOJ ADA Title II web rule. | Free | G1 (via 508 and ADA rule) |
| [U.S. Web Design System](https://designsystem.digital.gov/) | Federal design system and components; required under the 21st Century IDEA Act. | Free | G1 |
| [Digital Services Playbook](https://github.com/usds/playbook) (source repo; also mirrored at [tech.gsa.gov](https://tech.gsa.gov/guides/digital_services_playbook/)) and [TechFAR Hub](https://techfarhub.usds.gov/) | 13 plays for federal digital services; how to buy agile software under the FAR. | Free | G2 |
| [Digital.gov](https://digital.gov/) | Federal web policy, guides on plain language, analytics, performance, and the [Plain Writing Act](https://www.plainlanguage.gov/). | Free | G1/G2 |

## 15. Computing curricula (the academic BoKs)

These define what a degree in each field should cover. They are structured as knowledge areas → units → topics → learning outcomes, so they work as BoKs.

| BoK | Access | Gov |
|---|---|---|
| [ACM/IEEE/AAAI CS2023 Computer Science Curricula](https://csed.acm.org/) | Free | — |
| [ACM/IEEE SE2014 Software Engineering Curriculum (SEEK)](https://www.acm.org/education/curricula-recommendations) | Free | — |
| [ACM Cybersecurity Curricula 2017 (CSEC2017)](https://cybered.hosting.acm.org/wp/) | Free | G3 (NSA CAE program references) |
| [NSA/DHS Centers of Academic Excellence (CAE-C) Knowledge Units](https://www.caecommunity.org/) | Free | G1 (CAE designation) |
| [GSwE2009 Graduate Software Engineering curriculum](https://www.acm.org/education/curricula-recommendations) | Free | — |
| [ACM IT2017 / IS2020 / DS2021](https://www.acm.org/education/curricula-recommendations) | Free | — |

## 16. Crosswalks: how the compliance BoKs map to each other

The government compliance world is mostly one control catalog seen through different lenses. These crosswalks make that visible.

| Crosswalk | Maps |
|---|---|
| [NIST OLIR (Online Informative References) catalog](https://csrc.nist.gov/projects/olir/informative-reference-catalog) | CSF 2.0 and 800-53 ↔ ISO 27001, CIS Controls, HIPAA, CMMC, and others. |
| [NIST SP 800-53 Rev 5 to ISO/IEC 27001 mapping](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) (supplemental "mappings" spreadsheet) | 800-53 ↔ ISO 27001:2022 Annex A. |
| [CSF 2.0 Informative References](https://www.nist.gov/informative-references) | CSF ↔ 800-53, 800-171, CIS, and more. |
| [NIST SP 800-171r3 ↔ 800-53 tailoring](https://csrc.nist.gov/pubs/sp/800/171/r3/final) | Which moderate-baseline controls became CUI requirements. |
| [NICE ↔ DCWF](https://dodcio.defense.gov/Cyber-Workforce/DCWF) | NICE work roles ↔ DoD work role codes. |
| [Secure Controls Framework STRM](https://securecontrolsframework.com/) | 200+ frameworks, set-theory relationship mapping. |
| [SSDF ↔ other secure-SDLC frameworks](https://csrc.nist.gov/pubs/sp/800/218/final) (inside SP 800-218) | SSDF ↔ BSIMM, SAMM, ISO 27034, IEC 62443, and others. |

### The rough shape

```
            Law / policy                     Standard / catalog                 Program / audit
 FISMA, OMB A-130 ─────────────▶ FIPS 199/200, SP 800-53, RMF ──────▶ Agency ATO, IG FISMA audits (FISCAM)
 FAR/DFARS 7012 ───────────────▶ SP 800-171 (subset of 800-53) ─────▶ CMMC assessments
 FedRAMP Authorization Act ────▶ 800-53 + FedRAMP baselines ────────▶ FedRAMP 3PAO assessments
 EO 14028, OMB M-22-18 ────────▶ SP 800-218 SSDF ───────────────────▶ CISA attestation form
 DoDI 8140, DoDM 8140.03 ──────▶ NICE → DCWF work roles ────────────▶ Certs (Security+, CISSP, …)
 FMFIA, OMB A-123 ─────────────▶ GAO Green Book (COSO) ─────────────▶ Financial / IT audits (Yellow Book)
 DoDI 5000.x ──────────────────▶ DoD SE Guidebook (ISO 15288) ──────▶ Technical reviews, SEP
 Section 508, ADA Title II ────▶ WCAG 2.x ──────────────────────────▶ ICT testing baseline
```

---

## Aggregated BoKs

Paywalled BoKs whose free derivatives are scattered or thin. Each file outlines the full structure of the BoK, explains each part, and points to the best free material per part, with US government crosswalks where they exist.

| File | Source BoK |
|---|---|
| [pmbok.md](aggregated/pmbok.md) | PMI PMBOK Guide (7th/8th ed.) and the Process Groups practice guide |
| [babok.md](aggregated/babok.md) | IIBA BABOK Guide v3 |
| [itil-4.md](aggregated/itil-4.md) | ITIL 4 |
| [dama-dmbok.md](aggregated/dama-dmbok.md) | DAMA-DMBOK 2nd ed. (revised) |
| [cmmi.md](aggregated/cmmi.md) | CMMI v2.x / v3.0 |
| [cobit.md](aggregated/cobit.md) | ISACA COBIT 2019 |
| [iso-iec-27001-27002.md](aggregated/iso-iec-27001-27002.md) | ISO/IEC 27001:2022 and 27002:2022 |
| [iso-iec-ieee-12207-and-15288-life-cycle-processes.md](aggregated/iso-iec-ieee-12207-and-15288-life-cycle-processes.md) | ISO/IEC/IEEE 12207:2017 and 15288:2023 |
| [isc2-cissp-cbk.md](aggregated/isc2-cissp-cbk.md) | (ISC)² CISSP Common Body of Knowledge |
| [do-178c.md](aggregated/do-178c.md) | RTCA DO-178C and supplements |

## Link notes

- In 2025 the Department of Defense began using "Department of War" domains (e.g. `dowcio.war.gov`, `war.gov`). The `defense.gov` links above still resolved when this was written; if one breaks, try the same path on the `.war.gov` domain.
- 18F was shut down in 2025. Its guides may only be on archive mirrors.
- NIST CSRC links use the `/pubs/sp/800/<n>/…/final` pattern, which always points at the latest final version.
- Want to add one? Use the same row format and tags, and put it in the section closest to its main audience.
