# DAMA-DMBOK: Data Management Body of Knowledge (aggregated)

**Source BoK:** *DAMA-DMBOK: Data Management Body of Knowledge*, 2nd edition (2017), revised 2024 (DAMA International). A 3.0 effort was announced by DAMA in 2025.
**Why aggregated:** the book is paid. Federal data sources (Federal Data Strategy, DoD Data Strategy, NIST) are free but focus on policy and goals, not a full functional breakdown.
**Gov tie:** G3. Federal CDOs (required by the Evidence Act, 2019) and DoD data governance commonly borrow DMBOK's wheel; the CDMP certification is DMBOK-based.

## 1. The DAMA Wheel

**Data Governance** sits at the hub, surrounded by ten knowledge areas. Eleven total:

| # | Knowledge area | Definition (summarized) | Key activities | Best free sources |
|---|---|---|---|---|
| 1 | **Data Governance** | Exercise of authority, control, and shared decision making over data assets. | Define strategy; set policies & standards; stewardship roles (data owners, stewards, custodians); issue management; regulatory compliance; metrics. | [Federal Data Strategy practices](https://strategy.data.gov/); [CDO Council](https://www.cdo.gov/); [DoD Data Strategy](https://media.defense.gov/2020/Oct/08/2002514180/-1/-1/0/DOD-DATA-STRATEGY.PDF) |
| 2 | **Data Architecture** | Blueprints for managing data aligned with organizational strategy. | Enterprise data models; data flow designs; standards; integrate with EA. | [FEAF-II Data Reference Model](https://obamawhitehouse.archives.gov/sites/default/files/omb/assets/egov_docs/fea_v2.pdf); [NIST Big Data Reference Architecture (SP 1500-6)](https://www.nist.gov/itl/big-data-nist) |
| 3 | **Data Modeling & Design** | Discovering, analyzing, representing, communicating data requirements as a data model. | Conceptual → logical → physical models; relational, dimensional, NoSQL, object, fact-based. | [OMG UML](https://www.omg.org/spec/UML/); [NIEM (National Information Exchange Model)](https://www.niem.gov/) |
| 4 | **Data Storage & Operations** | Design, implementation, and support of stored data. | DBA work: backup/recovery, performance, replication, retention. | NIST SP 800-34 (backup/recovery); vendor docs |
| 5 | **Data Security** | Planning and execution of security policies to provide authentication, authorization, access, auditing. | Classification; access control; encryption; masking; auditing; privacy. | [NIST SP 800-53 AC, AU, SC, PT families](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final); [NIST Privacy Framework](https://www.nist.gov/privacy-framework); [CUI Registry](https://www.archives.gov/cui) |
| 6 | **Data Integration & Interoperability** | Movement and consolidation of data within and between stores, apps, organizations. | ETL/ELT, CDC, messaging, APIs, canonical models, hub-and-spoke. | [NIEM](https://www.niem.gov/); [DoD Data Strategy "Interoperable" goal](https://media.defense.gov/2020/Oct/08/2002514180/-1/-1/0/DOD-DATA-STRATEGY.PDF) |
| 7 | **Document & Content Management** | Lifecycle control of unstructured data (documents, records, email, media). | Records management, retention schedules, e-discovery, taxonomies. | [NARA records management guidance](https://www.archives.gov/records-mgmt); [Federal Records Act](https://www.archives.gov/about/laws/fed-agencies.html) |
| 8 | **Reference & Master Data** | Managing shared data to meet goals, reduce redundancy, and ensure quality via standard definitions. | Golden record; match/merge; reference code sets; data sharing agreements. | [GSA Unique Entity ID / SAM.gov data](https://sam.gov/); [data.gov](https://data.gov/) |
| 9 | **Data Warehousing & Business Intelligence** | Planning, implementation, control to provide decision support data. | Inmon vs Kimball; star schema; ODS; data marts; data lakes / lakehouse. | [Federal Data Strategy action plans](https://strategy.data.gov/); [Data.gov](https://data.gov/) |
| 10 | **Metadata Management** | Planning and control to enable high-quality integrated metadata. | Business, technical, operational metadata; catalogs; lineage. | [DCAT-US schema (Project Open Data)](https://resources.data.gov/resources/dcat-us/); [NIST SP 1500 series](https://www.nist.gov/itl/big-data-nist) |
| 11 | **Data Quality** | Planning and implementation of quality management techniques to measure, assess, improve data fitness for use. | Dimensions (accuracy, completeness, consistency, integrity, reasonability, timeliness, uniqueness, validity); profiling; root cause; DQ rules. | [Federal Committee on Statistical Methodology data quality framework](https://www.fcsm.gov/); [OMB Information Quality guidelines](https://www.whitehouse.gov/omb/information-resources/guidance/) |

DMBOK 2 also has chapters on **Data Handling Ethics**, **Big Data and Data Science**, **Data Management Maturity Assessment**, **Data Management Organization and Role Expectations**, and **Data Management and Organizational Change Management**.

## 2. The Environmental Factors Hexagon

Every knowledge area is described with the same seven parts (context diagram):

1. Goals and principles
2. Activities
3. Primary deliverables
4. Roles and responsibilities
5. Technology
6. Practices and techniques (methods)
7. Organization and culture

Context diagrams also list inputs, suppliers, participants, consumers, and metrics.

## 3. Maturity models (for assessment)

| Model | Access |
|---|---|
| DMBOK DMMA chapter | Paid (in book) |
| [CMMI Data Management Maturity (DMM)](https://cmmiinstitute.com/) | Paid (being folded into CMMI) |
| EDM Council DCAM | Free (reg.) summary |
| [Federal Data Strategy Data Governance Playbook](https://resources.data.gov/) | Free |
| [DoD Data Decrees (2021 "Creating Data Advantage" memo)](https://media.defense.gov/) | Free |

## 4. Federal legal anchors for data management

- **Foundations for Evidence-Based Policymaking Act (2018)**: CDOs, open data by default (OPEN Government Data Act), data inventories.
- **Federal Records Act** and **NARA** rules: records lifecycle.
- **Privacy Act of 1974**, E-Government Act §208 (PIAs), **OMB A-130** Appendix II.
- **CUI program (32 CFR 2002)**: marking and handling of sensitive unclassified data.
- **Information Quality Act**: data quality guidelines.

## 5. Crosswalk

| DMBOK area | Related |
|---|---|
| Data Governance | COBIT APO14 Managed Data (see [cobit.md](cobit.md)); ISO 8000 (data quality, paid) |
| Data Security | ISO/IEC 27002 (see [iso-iec-27001-27002.md](iso-iec-27001-27002.md)); NIST 800-53 |
| Data Architecture | TOGAF Phase C; FEAF DRM; DoDAF data views |
| Data Quality | ISO 8000; ISO/IEC 25012 (data quality model) |
