# ITIL 4 (aggregated)

**Source BoK:** ITIL 4 Foundation (2019) and the ITIL 4 practice guides, published by Axelos, now PeopleCert. ITIL 4 was refreshed in 2025 ("ITIL Version 5" announcements by PeopleCert; check [peoplecert.org](https://www.peoplecert.org/) for status).
**Why aggregated:** every ITIL publication is paid. [FitSM](https://www.fitsm.eu/) is a free, complete, lightweight ITSM standard and is the best single free derivative; this file maps ITIL onto it and onto federal sources.
**Gov tie:** G3. Federal help desk, NOC/SOC, and "IT operations and maintenance" contracts commonly require ITIL-aligned processes and ITIL-certified staff; ISO/IEC 20000-1 (the certifiable ITSM standard) is ITIL-aligned.

## 1. Key concepts

- **Service:** a means of enabling value co-creation by facilitating outcomes customers want, without the customer managing specific costs and risks.
- **Value co-creation:** value is created jointly by provider and consumer.
- **Utility** (fit for purpose) and **warranty** (fit for use: availability, capacity, security, continuity).
- **Outputs vs outcomes**, **costs** and **risks** introduced or removed.
- **Service offering, service relationship, service consumption, service provision.**

## 2. The four dimensions of service management

1. Organizations and people
2. Information and technology
3. Partners and suppliers
4. Value streams and processes

Each is shaped by external PESTLE factors.

## 3. The Service Value System (SVS)

Opportunity/demand → **SVS** → value. The SVS has five parts:

1. **Guiding principles** (below)
2. **Governance**
3. **Service value chain** (below)
4. **Practices** (below)
5. **Continual improvement**

### 3.1 Seven guiding principles

1. Focus on value
2. Start where you are
3. Progress iteratively with feedback
4. Collaborate and promote visibility
5. Think and work holistically
6. Keep it simple and practical
7. Optimize and automate

### 3.2 Service value chain activities

Plan · Improve · Engage · Design & Transition · Obtain/Build · Deliver & Support. Value streams are specific paths through these activities.

### 3.3 Continual improvement model

What is the vision? → Where are we now? → Where do we want to be? → How do we get there? → Take action → Did we get there? → How do we keep the momentum going?

## 4. The 34 practices

| Group | Practices |
|---|---|
| **General management (14)** | Architecture management; Continual improvement; Information security management; Knowledge management; Measurement and reporting; Organizational change management; Portfolio management; Project management; Relationship management; Risk management; Service financial management; Strategy management; Supplier management; Workforce and talent management |
| **Service management (17)** | Availability management; Business analysis; Capacity and performance management; Change enablement; Incident management; IT asset management; Monitoring and event management; Problem management; Release management; Service catalogue management; Service configuration management; Service continuity management; Service design; Service desk; Service level management; Service request management; Service validation and testing |
| **Technical management (3)** | Deployment management; Infrastructure and platform management; Software development and management |

### The practices that matter most (Foundation exam focus), with definitions

| Practice | Purpose | Key ideas |
|---|---|---|
| Incident management | Minimize negative impact of incidents by restoring normal operation ASAP. | Prioritize by impact and urgency; major incident procedure; swarming. |
| Problem management | Reduce likelihood and impact of incidents by finding causes and managing workarounds and known errors. | Phases: problem identification, problem control, error control. |
| Change enablement | Maximize successful changes by assessing risk, authorizing, and managing the schedule. | Standard (pre-authorized), normal, emergency changes; change authority. |
| Service request management | Support agreed quality by handling user-initiated, predefined requests. | Standardize and automate fulfilment. |
| Service desk | Capture demand for incident resolution and service requests; single point of contact. | Empathy, channels, self-service. |
| Service level management | Set business-based targets and ensure delivery is assessed and monitored. | SLAs, watermelon effect, customer engagement. |
| Monitoring & event management | Observe services and record/report changes of state (events). | Informational, warning, exception events. |
| IT asset management | Plan and manage full life cycle of IT assets. | Hardware, software licenses, cloud. |
| Service configuration management | Ensure accurate info on configuration items (CIs) and their relationships. | CMDB/CMS. |
| Release management | Make new and changed services available. | Release vs deployment. |
| Deployment management | Move components to live environments. | Phased, continuous, big bang, pull. |
| Information security management | Protect information needed by the organization. | Confidentiality, integrity, availability, authentication, non-repudiation. |
| Relationship management | Establish and nurture links with stakeholders. | |
| Supplier management | Ensure suppliers' performance supports seamless services. | |
| Continual improvement | Align practices and services with changing needs. | Continual improvement register. |

## 5. FitSM as the free derivative

[FitSM](https://www.fitsm.eu/) (part 0 overview & vocabulary, part 1 requirements, part 2 objectives & activities, part 3 roles, part 4 templates, parts 5–6 implementation and maturity) defines 14 processes that line up with ITIL practices:

| FitSM process | ITIL 4 practice(s) |
|---|---|
| Service Portfolio Management (SPM) | Portfolio management, Service catalogue management |
| Service Level Management (SLM) | Service level management |
| Service Reporting Management (SRM) | Measurement and reporting |
| Service Availability & Continuity Mgmt (SACM) | Availability management, Service continuity management |
| Capacity Management (CAPM) | Capacity and performance management |
| Information Security Management (ISM) | Information security management |
| Customer Relationship Management (CRM) | Relationship management |
| Supplier Relationship Management (SUPPM) | Supplier management |
| Incident & Service Request Management (ISRM) | Incident management, Service request management, Service desk |
| Problem Management (PM) | Problem management |
| Configuration Management (CONFM) | Service configuration management, IT asset management |
| Change Management (CHM) | Change enablement |
| Release & Deployment Management (RDM) | Release management, Deployment management |
| Continual Service Improvement Mgmt (CSI) | Continual improvement |

## 6. Federal sources that cover the same ground

| ITSM topic | Free federal source |
|---|---|
| Configuration management | [NIST SP 800-128](https://csrc.nist.gov/pubs/sp/800/128/upd1/final); 800-53 CM family; [MIL-HDBK-61B](https://quicksearch.dla.mil/) |
| Incident management | [NIST SP 800-61r3](https://csrc.nist.gov/pubs/sp/800/61/r3/final); [CISA Federal Incident & Vulnerability Response Playbooks](https://www.cisa.gov/resources-tools/resources/federal-government-cybersecurity-incident-and-vulnerability-response-playbooks) |
| Continuity / availability | [NIST SP 800-34](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final); [FEMA Federal Continuity Directives](https://www.fema.gov/emergency-managers/national-preparedness/continuity) |
| Asset management | [NIST SP 1800-5 IT Asset Management](https://www.nccoe.nist.gov/); [CISA CDM program](https://www.cisa.gov/resources-tools/programs/continuous-diagnostics-and-mitigation-cdm-program) |
| Service financial management | [TBM Taxonomy](https://www.tbmcouncil.org/learn-tbm/tbm-taxonomy/), used by OMB for IT spending |
| Monitoring / SRE | [Google SRE books](https://sre.google/books/) (free); NIST SP 800-137 continuous monitoring |

## 7. Crosswalk

| ITIL | Related |
|---|---|
| Whole | ISO/IEC 20000-1 (certifiable, paid); COBIT DSS domain (see [cobit.md](cobit.md)) |
| Information security mgmt | ISO/IEC 27001 (see [iso-iec-27001-27002.md](iso-iec-27001-27002.md)); NIST CSF |
| Change / release / deployment | DevOps / DevSecOps; DoD DevSecOps Fundamentals |
| Software development & mgmt | SWEBOK; ISO/IEC/IEEE 12207 |
