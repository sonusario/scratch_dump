# ISO/IEC/IEEE 12207 and 15288: life cycle processes (aggregated)

**Source BoKs:**
- ISO/IEC/IEEE 15288:2023 *Systems and software engineering — System life cycle processes*
- ISO/IEC/IEEE 12207:2017 *Systems and software engineering — Software life cycle processes*

**Why aggregated:** both are paid (ISO or IEEE). Excellent free derivatives exist, but each covers one angle: NIST SP 800-160 adds security to every 15288 process, SEBoK explains the processes, and the DoD SE Guidebook implements them for defense. This file lays out the full process set once and points each process to the best free source.
**Gov tie:** G3, very strong. 12207 descends from **MIL-STD-498 / DOD-STD-2167A** (DoD software development standards) via J-STD-016 and IEEE/EIA 12207. 15288 is the basis of the DoD SE technical and technical-management processes (DoDI 5000.88, DoD SE Guidebook), INCOSE's handbook, and NIST SP 800-160.

## 1. Shape of the standards

Since 2017, 12207 and 15288 share **the same 30 processes** in the same four groups (12207 words them for software, 15288 for systems). 15288:2023 updated the system version; 12207:2017 is still current for software.

## 2. The 30 processes, with free sources per process

Legend for sources:
- **SEBoK** = [Guide to the Systems Engineering Body of Knowledge](https://sebokwiki.org/)
- **800-160** = [NIST SP 800-160 Vol. 1 Rev. 1](https://csrc.nist.gov/pubs/sp/800/160/v1/r1/final) (appendix per process; adds security outcomes)
- **DoD SE** = [DoD Systems Engineering Guidebook (2022)](https://www.cto.mil/wp-content/uploads/2023/06/SE-Guidebook-2022.pdf), ch. 4
- **NASA** = [NASA SE Handbook](https://www.nasa.gov/reference/systems-engineering-handbook/)
- **SWEBOK** = [SWEBOK v4](https://www.computer.org/education/bodies-of-knowledge/software-engineering)

### 2.1 Agreement processes (2)

| Process | Purpose | Best free sources |
|---|---|---|
| Acquisition | Obtain a product or service per acquirer's requirements. | FAR; [DoD AAF](https://aaf.dau.edu/); 800-160 §3.1.1 |
| Supply | Provide an acquirer with a product or service that meets agreed requirements. | 800-160 §3.1.2; [DAU Acquipedia](https://www.dau.edu/acquipedia-home) |

### 2.2 Organizational project-enabling processes (6)

| Process | Purpose | Best free sources |
|---|---|---|
| Life Cycle Model Management | Define, maintain, assure availability of policies, life cycle processes, models, procedures. | SEBoK "Life Cycle Models"; 800-160 |
| Infrastructure Management | Provide infrastructure and services to projects. | 800-160 |
| Portfolio Management | Initiate and sustain necessary, sufficient, suitable projects. | OMB CPIC; COBIT APO05 ([cobit.md](cobit.md)) |
| Human Resource Management | Provide necessary human resources and maintain competencies. | NICE / DCWF; [SWECOM](https://computer.org/volunteering/boards-and-committees/professional-educational-activities/software-engineering-competency-model) |
| Quality Management | Assure products, services, and process implementations meet quality objectives. | SWEBOK Software Quality KA; [NASA quality](https://sma.nasa.gov/sma-disciplines/quality) |
| Knowledge Management | Create capability and assets to exploit existing knowledge. | NASA lessons learned ([LLIS](https://llis.nasa.gov/)) |

### 2.3 Technical management processes (8)

| Process | Purpose | Best free sources |
|---|---|---|
| Project Planning | Produce and coordinate effective, workable plans. | DoD SE (SEP outline); GAO Schedule & Cost Guides; [pmbok.md](pmbok.md) |
| Project Assessment and Control | Assess plans are aligned and feasible; determine status; direct execution. | DoD SE (technical reviews, TPMs); GAO Agile Guide |
| Decision Management | Provide a structured framework to identify, characterize and evaluate alternatives. | DoD SE; SEBoK "Decision Management"; NASA §6.8 |
| Risk Management | Identify, analyze, treat, and monitor risks continually. | DoD Risk, Issue & Opportunity Guide; NIST SP 800-30 for security risk |
| Configuration Management | Manage and control system elements and configurations over the life cycle. | [MIL-HDBK-61B](https://quicksearch.dla.mil/); NIST SP 800-128; SWEBOK SCM KA |
| Information Management | Generate, obtain, confirm, transform, retain, retrieve, disseminate, dispose information. | NARA records guidance; DAMA ([dama-dmbok.md](dama-dmbok.md)) |
| Measurement | Collect, analyze, report objective data. | [PSM guides](https://www.psmsc.com/); ISO 15939 summary in SWEBOK |
| Quality Assurance | Help ensure effective application of the QM process to the project. | SWEBOK; CMMI PPQA ([cmmi.md](cmmi.md)) |

### 2.4 Technical processes (14)

| Process | Purpose | Best free sources |
|---|---|---|
| Business or Mission Analysis | Define the problem/opportunity, characterize the solution space, select a solution class. | DoD SE; SEBoK "Business or Mission Analysis"; JCIDS via DAU |
| Stakeholder Needs and Requirements Definition | Define stakeholder requirements for a system that provides needed capabilities. | SEBoK; NASA §4.1; [babok.md](babok.md) |
| System / Software Requirements Definition | Transform the stakeholder, user-oriented view into a technical view of a solution. | SWEBOK Requirements KA; NASA §4.2; [NASA SWEHB](https://swehb.nasa.gov/) |
| Architecture Definition | Generate architecture alternatives, select one, express it in consistent views. | SWEBOK Architecture KA; [SEI architecture library](https://insights.sei.cmu.edu/library/); DoDAF |
| Design Definition | Provide sufficient detailed data and information about the system and its elements. | SWEBOK Design KA; NASA §4.4 |
| System Analysis | Provide a rigorous basis of data and information for technical understanding. | SEBoK "System Analysis"; NASA |
| Implementation | Realize a specified system element. | SWEBOK Construction KA; CERT secure coding; SSDF |
| Integration | Synthesize a set of system elements into a realized system. | NASA §5.2; DoD SE |
| Verification | Provide objective evidence that a system or element fulfils its specified requirements. | SWEBOK Testing KA; ISTQB syllabi; NASA §5.3 |
| Transition | Establish capability to provide services specified by stakeholder requirements in the operational environment. | NASA §5.5; ITIL release/deployment ([itil-4.md](itil-4.md)) |
| Validation | Provide objective evidence that the system fulfils its business/mission objectives and stakeholder requirements in its intended operational environment. | NASA §5.4; DoD OT&E (DOT&E) |
| Operation | Use the system to deliver its services. | ITIL; Google SRE books |
| Maintenance | Sustain the capability of the system to provide a service. | SWEBOK Maintenance KA; DoD sustainment (DAU) |
| Disposal | End the existence of a system element or system for a specified intended use. | NIST SP 800-88 (media sanitization); NASA |

## 3. Life cycle stages (ISO/IEC/IEEE 24748-1)

Concept → Development → Production → Utilization → Support → Retirement. Processes are not stages: any process can occur in any stage.

## 4. Related standards in the family (paid; free summaries noted)

| Standard | Topic | Free summary / derivative |
|---|---|---|
| ISO/IEC/IEEE 24748-1 to -9 | Life cycle management guidance, application of 15288/12207 | SEBoK |
| ISO/IEC/IEEE 29148 | Requirements engineering | SWEBOK Requirements KA; NASA Appendix C (how to write a good requirement) |
| ISO/IEC/IEEE 42010 | Architecture description | [Free overview by the 42010 WG](http://www.iso-architecture.org/42010/) |
| ISO/IEC/IEEE 29119 | Software testing | ISTQB syllabi |
| ISO/IEC/IEEE 15289 | Content of life cycle information items (documentation) | [MIL-STD-498 DIDs](https://quicksearch.dla.mil/) (free predecessors) |
| ISO/IEC/IEEE 16326 | Project management | [pmbok.md](pmbok.md) |
| ISO/IEC/IEEE 15939 | Measurement | PSM guides |
| ISO/IEC/IEEE 14764 | Software maintenance | SWEBOK Maintenance KA |
| ISO/IEC/IEEE 16085 | Risk management | DoD RIO guide |
| ISO/IEC/IEEE 24765 | Vocabulary (SEVOCAB) | [SEVOCAB online (free)](https://pascal.computer.org/sev_display/index.action) |
| IEEE 1012 | Verification & validation (IV&V) | NASA IV&V program; SWEBOK |
| IEEE 828 | Configuration management | MIL-HDBK-61B |

## 5. DoD's 16 SE processes (DoD SE Guidebook) vs ISO 15288

| DoD technical management (8) | ISO 15288 |
|---|---|
| Technical Planning | Project Planning |
| Decision Analysis | Decision Management |
| Technical Assessment | Project Assessment and Control |
| Requirements Management | (within Stakeholder/System Requirements Definition) |
| Risk Management | Risk Management |
| Configuration Management | Configuration Management |
| Technical Data Management | Information Management |
| Interface Management | (within Architecture/Integration) |

| DoD technical (8) | ISO 15288 |
|---|---|
| Stakeholder Requirements Definition | Stakeholder Needs and Requirements Definition |
| Requirements Analysis | System Requirements Definition |
| Architecture Design | Architecture Definition |
| Implementation | Implementation |
| Integration | Integration |
| Verification | Verification |
| Validation | Validation |
| Transition | Transition |
