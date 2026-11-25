# Domain 5: Security Program Management and Oversight (20%)

[Back to the map](README.md)

Governance and compliance are the hardest parts of Security+ to make playable. The game's approach: put the player in the meeting where the decision is made, give them the document to write, and let the consequences show up later in an audit or an incident.

## 5.1 Summarize elements of effective security governance

**Teaching approach.** S32 has the player rebuild Ridgeway's policy library in the Docs app, sorting existing documents into guidelines, policies, standards and procedures, and filling gaps from templates. Each document type has a fixed shape so the difference is visible. S06 and S32 assign data roles. External considerations appear when a law or regulator affects a decision (S20 breach notification, S25 examiner, S26 GDPR).

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Guidelines | S32 | Sort a "recommended practices" doc | Recommended, non-mandatory advice → Guidelines |
| Policy: acceptable use policy (AUP) | S01 | Sign it; later enforce it | A policy defining allowed use of company systems → AUP |
| Information security policies | S32 | Write the top-level policy | The high-level statement of an organization's security goals and rules → Information security policy |
| Business continuity | S38 | Use the BC policy during the attack | A policy for keeping the business running in a disruption → Business continuity policy |
| Disaster recovery | S22 | DR policy names RTOs | A policy for restoring IT after a disaster → Disaster recovery policy |
| Incident response | S23 | Update IR policy | A policy that defines how incidents are handled and who is responsible → Incident response policy |
| Software development lifecycle (SDLC) | S12 | Paperkite's secure SDLC policy | A policy requiring security at every stage of building software → SDLC policy |
| Change management | S07 | The CAB policy | A policy requiring changes to be reviewed and approved → Change management policy |
| Standards: password | S04 | Password standard sets length 14+ | A mandatory, specific rule like "passwords must be at least 14 characters" is a ______. → Standard |
| Access control | S32 | Access control standard | A standard defining how access is requested, approved and reviewed → Access control standard |
| Physical security | S10 | Physical security standard for sites | A standard defining locks, badges and visitor rules → Physical security standard |
| Encryption | S33 | Encryption standard (AES-256, TLS 1.2+) | A standard listing approved algorithms and key lengths → Encryption standard |
| Procedures: change management | S07 | Step-by-step for the CAB | Step-by-step instructions to carry out a policy → Procedure |
| Onboarding/offboarding | T03, T04 | Checklists in Ticketing | A procedure for granting and removing access when people join or leave → Onboarding/offboarding |
| Playbooks | T17, S18 | Ransomware playbook | Step-by-step response instructions for a specific incident type → Playbook |
| External considerations: regulatory | S25 | Examiner | Rules from government agencies an organization must follow → Regulatory |
| Legal | S20 | Counsel on breach notification | Obligations from laws and contracts → Legal |
| Industry | S25 | PCI DSS | PCI DSS is an ______ standard, not a law. → Industry |
| Local/regional | S32 | County ordinance on records | State breach notification laws are ______ considerations. → Local/regional |
| National | S39 | Federal reporting requirements for critical infrastructure | Country-wide laws such as HIPAA in the US → National |
| Global | S26 | GDPR applies to EU customers | Laws that apply across borders, such as GDPR → Global |
| Monitoring and revision | S23, S32 | Annual policy review cycle | Policies should be reviewed regularly and after major ______. → Incidents/changes |
| Governance structures: boards | S40 | Board briefing | The top governing body that oversees risk and strategy → Board |
| Committees | S07, S32 | CAB, security steering committee | A group formed to oversee a specific area, such as security or change → Committee |
| Government entities | S32, S39 | County commission; federal agency | Public agencies that set rules or oversee public organizations → Government entities |
| Centralized/decentralized | S32 | Ridgeway central IT vs departments | Governance where one group sets all security policy → Centralized |
| Roles: owners | S06, S32 | Gloria owns land records | The senior person accountable for a data set's classification and protection → Data owner |
| Controllers | S26 | Paperkite decides why and how customer data is processed | The entity that decides the purposes and means of processing personal data → Data controller |
| Processors | S26, S27 | Lantern processes data on clients' behalf | The entity that processes personal data on behalf of a controller → Data processor |
| Custodians/stewards | S06 | Theo runs the backups | The person who handles day-to-day care of data, like backups → Data custodian/steward |

## 5.2 Explain elements of the risk management process

**Teaching approach.** S30 has the player and Marcus build Lantern's risk register in Docs with a built-in calculator. Risks the player creates (or ignores) across the campaign end up in the register, and accepted risks come back as incidents in Acts 3 to 5. S22 runs a BIA for Harbor. Quantitative risk cards use real arithmetic with the Typed card kind.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Risk identification | S30 | Walk through each client listing risks | Finding and listing risks that could affect the organization → Risk identification |
| Risk assessment: ad hoc | S16 | After the vendor news | An assessment done when needed, not on a schedule → Ad hoc |
| Recurring | S30 | Annual | An assessment done on a regular schedule → Recurring |
| One-time | S12 | Before Paperkite's launch | An assessment done once, e.g., for a project → One-time |
| Continuous | S28 | Ongoing monitoring | Ongoing, automated assessment of risk → Continuous |
| Risk analysis: qualitative | S30 | High/medium/low heat map | Risk analysis using ratings like high, medium, low → Qualitative |
| Quantitative | S30 | Dollar values | Risk analysis using numbers and money → Quantitative |
| Single loss expectancy (SLE) | S30 | Calculator | SLE = asset value × ______. → Exposure factor |
| Annualized loss expectancy (ALE) | S30 | Calculator | ALE = SLE × ______. → ARO |
| Annualized rate of occurrence (ARO) | S30 | Calculator | A laptop theft expected once every 4 years has an ARO of ______. → 0.25 |
| Probability | S30 | Rate on the heat map | The chance that a risk will occur, often a number from 0 to 1 → Probability |
| Likelihood | S30 | Rate on the heat map | A qualitative measure of how likely a risk is → Likelihood |
| Exposure factor | S30 | Percent of asset lost | If a flood would destroy 40% of a $100,000 asset, the EF is ______. → 40% (SLE $40,000) |
| Impact | S30 | Rate on the heat map | The harm caused if a risk happens → Impact |
| Risk register | S30 | Docs register | A document listing risks, owners, ratings and responses → Risk register |
| Key risk indicators | S30 | Choose KRIs and connect to SIEM metrics | Metrics that warn when a risk is increasing → Key risk indicators (KRIs) |
| Risk owners | S30 | Assign | The person accountable for managing a specific risk → Risk owner |
| Risk threshold | S30 | Set the line above which a risk needs action | The level of risk that triggers action → Risk threshold |
| Risk tolerance | S30 | Per-risk acceptable deviation | The acceptable variation around a specific risk → Risk tolerance |
| Risk appetite: expansionary | S40 | Paperkite's growth mode | A willingness to take more risk for growth → Expansionary appetite |
| Conservative | S40 | Copperline and Brightwater | A low willingness to take risk → Conservative appetite |
| Neutral | S40 | Lantern | A balanced approach to risk → Neutral appetite |
| Strategy: transfer | S30 | Cyber insurance | Moving risk to another party, e.g., insurance → Transfer |
| Accept | S30 | Live with low risk | Choosing to live with a risk because the cost of fixing it is higher → Accept |
| Accept: exemption | S30, T11 | Exempt a system from a policy | A formal release from having to meet a requirement → Exemption |
| Accept: exception | T11 | Temporary deviation with expiry | A temporary, approved deviation from policy → Exception |
| Avoid | S30 | Stop the risky activity (Paperkite drops a feature) | Stopping the activity that causes the risk → Avoid |
| Mitigate | S30 | Add controls | Reducing likelihood or impact with controls → Mitigate |
| Risk reporting | S40 | Board report | Communicating risk status to leadership → Risk reporting |
| Business impact analysis: recovery time objective (RTO) | S22 | Set and test | The maximum acceptable time to restore a system → RTO |
| Recovery point objective (RPO) | S22 | Set and test | The maximum acceptable data loss measured in time → RPO |
| Mean time to repair (MTTR) | S22 | Measure restore time | The average time to fix a failed system → MTTR |
| Mean time between failures (MTBF) | S38 | Pump reliability data | The average time a system runs between failures → MTBF |

## 5.3 Explain the processes associated with third-party risk assessment and management

**Teaching approach.** S27 flips the perspective: Copperline assesses Lantern, so the player answers a questionnaire and hosts the auditor. S16 shows what weak vendor management costs. T10 has the player assess vendors for clients. Agreement types are taught as documents in the Docs app with distinct shapes.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Vendor assessment: penetration testing | S27 | Copperline asks for Lantern's latest pentest | Asking a vendor for recent pentest results is part of vendor ______. → Assessment |
| Right-to-audit clause | S27 | Find it in the contract; Copperline exercises it | A contract term allowing the customer to audit the vendor → Right-to-audit clause |
| Evidence of internal audits | S27 | Provide Lantern's internal audit report | Proof that a vendor checks its own controls → Evidence of internal audits |
| Independent assessments | S27 | Lantern's SOC 2 report | An assessment by an outside party, such as a SOC 2 report → Independent assessment |
| Supply chain analysis | S34 | Map Brightwater's SCADA vendor's own suppliers | Examining risks in a vendor's own suppliers → Supply chain analysis |
| Vendor selection: due diligence | T10 | Check a new backup vendor | Investigating a vendor before signing → Due diligence |
| Conflict of interest | T10 | Femi's brother-in-law owns the vendor | When a decision-maker has a personal stake in a vendor → Conflict of interest |
| Agreement types: service-level agreement (SLA) | S27 | Lantern's response time commitments | A contract defining measurable service levels like uptime → SLA |
| Memorandum of agreement (MOA) | S39 | Brightwater and a neighboring utility agree on mutual aid | A document of agreed responsibilities, more formal than an MOU → MOA |
| Memorandum of understanding (MOU) | S39 | Information sharing with the ISAC | An informal statement of shared intent between parties → MOU |
| Master service agreement (MSA) | S27 | Lantern–Copperline umbrella contract | An umbrella contract with general terms for future work → MSA |
| Work order (WO)/statement of work (SOW) | S29 | Jules's pentest SOW | A document defining specific work, deliverables and timelines → SOW |
| Non-disclosure agreement (NDA) | S29 | Jules signs one | A contract to keep shared information confidential → NDA |
| Business partners agreement (BPA) | S39 | Joint venture between two utilities | An agreement defining how business partners share profits, losses and responsibilities → BPA |
| Vendor monitoring | S27 | Ongoing review of SLA metrics and news | Continuously watching a vendor's performance and security after signing → Vendor monitoring |
| Questionnaires | S27, T10 | Fill and review | A standard set of security questions sent to vendors → Security questionnaire |
| Rules of engagement | S29 | Scope, times, contacts for the pentest | The defined scope, methods and limits of a test or engagement → Rules of engagement |

## 5.4 Summarize elements of effective security compliance

**Teaching approach.** S25 (regulator) and S26 (SOC 2 and GDPR) put compliance under pressure. T15 data-subject requests recur. Consequences are shown in-world as fines, sanctions and trust damage when the player cuts corners.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Compliance reporting: internal | S25 | Report to Copperline's board | Compliance status reported to management → Internal reporting |
| External | S25, S39 | Report to the regulator | Compliance status reported to regulators or customers → External reporting |
| Consequences of non-compliance: fines | S25 | Examiner's finding with a fine | Monetary penalties for non-compliance → Fines |
| Sanctions | S25 | Restrictions on new products | Penalties restricting what an organization may do → Sanctions |
| Reputational damage | S20 | News story about Harbor | Loss of public trust after a breach → Reputational damage |
| Loss of license | S25 | Threat to Copperline's charter | The most severe consequence for a regulated business → Loss of license |
| Contractual impacts | S27 | A client cancels due to SLA breach | Penalties or termination under a contract → Contractual impacts |
| Compliance monitoring: due diligence/care | S25 | Show reasonable steps were taken | Taking reasonable steps to protect assets and meet obligations → Due care |
| Attestation and acknowledgement | S01, S25 | Staff sign that they read the policy | Formal confirmation that someone read and agrees to a policy → Attestation/acknowledgement |
| Internal and external | S25 | Internal compliance team vs examiner | Compliance checks run by your own staff vs outside parties → Internal and external monitoring |
| Automation | S28 | Continuous compliance dashboards | Using tools to continuously check compliance → Automation |
| Privacy: legal implications (local/regional, national, global) | S20, S26 | State breach law, HIPAA, GDPR | Privacy laws can apply at the local, national and ______ level. → Global |
| Data subject | T15 | A patient asks for their records | The individual whom personal data is about → Data subject |
| Controller vs processor | S26 | See 5.1 | Paperkite decides how customer data is used; its hosting provider is the ______. → Processor |
| Ownership | S26 | Who owns the customer data | Who is ultimately responsible for personal data? → Data owner/controller |
| Data inventory and retention | T15, S32 | Find all copies before answering a request | Knowing what personal data you hold and how long you keep it → Data inventory and retention |
| Right to be forgotten | T15 | Erasure request under GDPR | A person's right to have their personal data deleted → Right to be forgotten |

## 5.5 Explain types and purposes of audits and assessments

**Teaching approach.** S25, S26 and S27 are three different audits from three angles. S29 is the penetration test with Jules, which covers test types and reconnaissance hands-on in a range where everything is in scope by written agreement.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Attestation | S26 | Auditor signs the SOC 2 report | A formal statement by an auditor that controls meet a standard → Attestation |
| Internal: compliance | S25 | Copperline's compliance team pre-check | An organization's own check that it meets requirements → Internal compliance audit |
| Audit committee | S25 | Present findings to the committee | The board group that oversees audits → Audit committee |
| Self-assessments | S26 | Paperkite's readiness self-assessment | An organization evaluating its own controls → Self-assessment |
| External: regulatory | S25 | Examiner | An audit by a government regulator → Regulatory audit |
| Examinations | S25 | Formal exam | A formal review by a regulator → Examination |
| Assessment | S27 | Copperline assesses Lantern | An evaluation of controls by an outside party → External assessment |
| Independent third-party audit | S26 | SOC 2 auditor | An audit by an independent firm → Independent third-party audit |
| Penetration testing: physical | S37 (aftermath), S29 | Jules tests Ridgeway's front desk | Testing physical controls like locks and guards → Physical pentest |
| Offensive | S29 | Red team | Attack-side testing → Offensive (red team) |
| Defensive | S29 | Blue team | Defense-side testing and response → Defensive (blue team) |
| Integrated | S29 | Purple team exercise | Red and blue teams working together → Integrated (purple team) |
| Known environment | S29 | Jules has full docs | A test where testers get full information → Known environment (white box) |
| Partially known environment | S29 | Some info | A test with limited information → Partially known (gray box) |
| Unknown environment | S29 | No info | A test with no prior information → Unknown environment (black box) |
| Reconnaissance: passive | S29 | OSINT on Ridgeway, no packets sent | Gathering information without touching the target → Passive reconnaissance |
| Active | S29 | Scan in-scope hosts in the range | Directly probing the target, e.g., port scans → Active reconnaissance |

## 5.6 Given a scenario, implement security awareness practices

**Teaching approach.** The player is first a trainee (S01, S05) and later runs Copperline's and Harbor's awareness programs. In S05 the player builds a phishing campaign in a fictional training tool (to the client's own staff, with approval), reads the results, and designs follow-up training. Anomalous behavior is taught through NPCs whose behavior the player must classify.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Phishing: campaigns | S05 | Build an approved simulated campaign | Sending simulated phishing emails to test and train staff → Phishing campaign |
| Recognizing a phishing attempt | S05, T01 | Inspect sender, links, urgency | Urgency, mismatched sender domains and unexpected attachments are signs of ______. → Phishing |
| Responding to reported suspicious messages | T01 | Triage, block, thank the reporter | After a user reports a phish, the SOC should ______. → Analyze it, block indicators, and remove copies |
| Anomalous behavior recognition: risky | S24 | NPC disables antivirus to "speed up" their PC | Behavior that knowingly increases risk → Risky |
| Unexpected | S24 | Dale logs in at 3 a.m. | Behavior that differs from a user's normal pattern → Unexpected |
| Unintentional | S05 | Teller emails the wrong customer | A mistake without bad intent → Unintentional |
| User guidance and training: policy/handbook | S01 | Employee handbook | The document that tells staff the rules they must follow → Policy/handbook |
| Situational awareness | S37, T09 | Notice the person following you through the door | Being aware of surroundings to spot threats like tailgating → Situational awareness |
| Insider threat | S24 | Training module after Dale | Training staff to recognize and report insider risk → Insider threat training |
| Password management | S04 | Teach Harbor staff password managers | Training on strong, unique passwords and managers → Password management |
| Removable media and cables | S03 | "Free charging cable" at a conference | Don't plug in found USB drives or untrusted ______. → Cables |
| Social engineering | S05 | Module after vishing | Training on manipulation tactics like pretexting → Social engineering |
| Operational security | S36 | Staff post plant photos on social media | Protecting details that attackers could piece together → Operational security (OPSEC) |
| Hybrid/remote work environments | S11 | Home Wi-Fi, shoulder surfing in cafés | Training on securing home networks and public spaces → Hybrid/remote work |
| Reporting and monitoring: initial | S05 | Baseline click rate | Measuring before training starts → Initial |
| Recurring | S05, S23 | Quarterly metrics | Regularly measuring awareness over time → Recurring |
| Development | S05 | Build the training program | Creating training content tailored to roles and risks → Development |
| Execution | S05 | Deliver and track completion | Delivering training and tracking completion → Execution |
