# BABOK: Business Analysis Body of Knowledge (aggregated)

**Source BoK:** *A Guide to the Business Analysis Body of Knowledge* (BABOK Guide) v3, International Institute of Business Analysis (IIBA), 2015.
**Why aggregated:** the PDF is free only to IIBA members. Free sources cover pieces (requirements engineering in SWEBOK, user research in federal guides), but not the whole BA structure.
**Gov tie:** low directly. In federal work, BA activities show up as requirements development in DoD SE, business process reengineering for business systems (DoDI 5000.75), and user research in digital service teams.

## 1. Core model: BACCM

The Business Analysis Core Concept Model has six concepts. Every task in BABOK touches all six.

| Concept | Meaning |
|---|---|
| **Change** | The act of transformation in response to a need. |
| **Need** | A problem or opportunity to be addressed. |
| **Solution** | A specific way of satisfying needs in a context. |
| **Stakeholder** | A group or individual with a relationship to the change, need, or solution. |
| **Value** | The worth, importance, or usefulness of something to a stakeholder. |
| **Context** | The circumstances that influence and are influenced by the change. |

## 2. Requirement types

- **Business requirements:** goals and objectives of the organization.
- **Stakeholder requirements:** needs of particular stakeholders.
- **Solution requirements:** functional and non-functional (quality of service).
- **Transition requirements:** temporary capabilities needed to move from current to future state (data conversion, training).

## 3. The six knowledge areas and 30 tasks

### 3.1 Business Analysis Planning and Monitoring
1. Plan Business Analysis Approach
2. Plan Stakeholder Engagement
3. Plan Business Analysis Governance
4. Plan Business Analysis Information Management
5. Identify Business Analysis Performance Improvements

### 3.2 Elicitation and Collaboration
1. Prepare for Elicitation
2. Conduct Elicitation
3. Confirm Elicitation Results
4. Communicate Business Analysis Information
5. Manage Stakeholder Collaboration

### 3.3 Requirements Life Cycle Management
1. Trace Requirements
2. Maintain Requirements
3. Prioritize Requirements
4. Assess Requirements Changes
5. Approve Requirements

### 3.4 Strategy Analysis
1. Analyze Current State
2. Define Future State
3. Assess Risks
4. Define Change Strategy

### 3.5 Requirements Analysis and Design Definition (RADD)
1. Specify and Model Requirements
2. Verify Requirements
3. Validate Requirements
4. Define Requirements Architecture
5. Define Design Options
6. Analyze Potential Value and Recommend Solution

### 3.6 Solution Evaluation
1. Measure Solution Performance
2. Analyze Performance Measures
3. Assess Solution Limitations
4. Assess Enterprise Limitations
5. Recommend Actions to Increase Solution Value

## 4. Underlying competencies

Analytical thinking and problem solving; behavioural characteristics; business knowledge; communication skills; interaction skills; tools and technology.

## 5. The 50 techniques

Grouped here by purpose (BABOK lists them alphabetically). Free sources for each group are in the right column.

| Purpose | Techniques | Best free sources |
|---|---|---|
| Elicitation | Brainstorming, Document Analysis, Focus Groups, Interface Analysis, Interviews, Observation, Survey/Questionnaire, Workshops, Prototyping, Collaborative Games | [18F Methods (archived)](https://methods.18f.gov/), [Digital.gov research](https://digital.gov/topics/research/), [IREB handbook](https://cpre.ireb.org/en/downloads-and-resources/downloads) |
| Modelling (process, data, behaviour) | Process Modelling, Data Modelling, Data Dictionary, Data Flow Diagrams, Sequence Diagrams, State Modelling, Use Cases and Scenarios, User Stories, Scope Modelling, Business Rules Analysis, Decision Modelling, Glossary, Organizational Modelling, Roles and Permissions Matrix | [OMG BPMN 2.0 spec](https://www.omg.org/spec/BPMN/), [OMG DMN spec](https://www.omg.org/spec/DMN/), [OMG UML spec](https://www.omg.org/spec/UML/), [OMG SBVR](https://www.omg.org/spec/SBVR/) (all free) |
| Strategy | SWOT, Business Capability Analysis, Business Model Canvas, Business Cases, Benchmarking and Market Analysis, Root Cause Analysis, Value Stream Mapping, Concept Modelling, Mind Mapping | [FIBF capability models](https://ussm.gsa.gov/fibf/), [NIST Baldrige](https://www.nist.gov/baldrige) |
| Prioritization & decision | Prioritization (MoSCoW, ranking, time-boxing), Decision Analysis, Financial Analysis (NPV, IRR, payback), Risk Analysis and Management, Estimation | [OMB Circular A-94 (benefit-cost analysis)](https://www.whitehouse.gov/omb/information-resources/guidance/), [GAO Cost Guide](https://www.gao.gov/products/gao-20-195g) |
| Requirements quality & management | Acceptance and Evaluation Criteria, Backlog Management, Item Tracking, Lessons Learned, Reviews, Non-Functional Requirements Analysis, Metrics and KPIs, Balanced Scorecard | [SWEBOK Requirements KA](https://www.computer.org/education/bodies-of-knowledge/software-engineering), [ISO/IEC 25010 quality model (summary)](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010) |
| Stakeholders & organization | Stakeholder List/Map/Personas, RACI, Functional Decomposition, Vendor Assessment | [Digital.gov personas](https://digital.gov/topics/research/) |

## 6. Perspectives (how BA changes by context)

1. **Agile:** backlog refinement, just-in-time detail, user stories, story mapping.
2. **Business Intelligence:** data-to-decision chains, data warehouse requirements.
3. **Information Technology:** systems integration, COTS selection, NFRs.
4. **Business Architecture:** capability maps, value streams, enterprise-level change.
5. **Business Process Management:** process discovery, BPMN, continuous improvement.

## 7. Free federal equivalents worth knowing

- **DoD business systems:** [DoDI 5000.75 Business Systems Requirements and Acquisition](https://www.esd.whs.mil/Portals/54/Documents/DD/issuances/dodi/500075p.pdf) defines business process reengineering, capability requirements, and the "Business Capability Acquisition Cycle" (BCAC), essentially BA for DoD. Guidance at [aaf.dau.edu (DBS pathway)](https://aaf.dau.edu/).
- **Requirements in DoD SE:** the [DoD SE Guidebook](https://www.cto.mil/wp-content/uploads/2023/06/SE-Guidebook-2022.pdf) Stakeholder Requirements Definition and Requirements Analysis processes.
- **JCIDS** (Joint Capabilities Integration and Development System) for warfighting requirements: [DAU Acquipedia](https://www.dau.edu/acquipedia-home).
- **Agile requirements in government:** [GAO Agile Assessment Guide](https://www.gao.gov/products/gao-24-105506), ch. on requirements.

## 8. Crosswalk

| BABOK | Related |
|---|---|
| Elicitation, RADD | SWEBOK Software Requirements; ISO/IEC/IEEE 29148 (requirements engineering; paid); IREB CPRE |
| Requirements Life Cycle Mgmt | PMBOK Scope Mgmt (see [pmbok.md](pmbok.md)); CMMI Requirements Development and Management (see [cmmi.md](cmmi.md)) |
| Strategy Analysis | TOGAF ADM phases A–B; FEAF business reference model |
| Solution Evaluation | ITIL Continual Improvement (see [itil-4.md](itil-4.md)) |
