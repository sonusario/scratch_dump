# 6. Objective-to-scenario map

This folder maps **every SY0-701 objective, and every concept CompTIA lists under it**, to the scenarios that teach it, the beat types used, and example cards or checked tasks.

## How to read the domain files

Each objective has a table with one row per listed concept:

| Column | Meaning |
|--------|---------|
| **Concept** | The term or sub-bullet from the exam objectives |
| **Scenarios** | Story scenario ids (S01 to S40, listed below) and side-ticket ids (T01 and up). The first id is where the concept is introduced. |
| **How it is taught** | What the player does: the beat types (Inspect, Place, Computer, Card, Decision, Dialogue) and the specific task |
| **Example card** | One card front → back. Each concept will have two to four variants in the real deck. |

The **concept id** used in content files is `<objective>.<slug>`, for example `1.1.control_type.compensating`. The coverage check in the [content pipeline](../07_content_model_and_pipeline.md#coverage-check) uses these ids.

## Domain files

- [Domain 1: General Security Concepts](domain_1_general_security_concepts.md)
- [Domain 2: Threats, Vulnerabilities, and Mitigations](domain_2_threats_vulnerabilities_mitigations.md)
- [Domain 3: Security Architecture](domain_3_security_architecture.md)
- [Domain 4: Security Operations](domain_4_security_operations.md)
- [Domain 5: Security Program Management and Oversight](domain_5_program_management_oversight.md)
- [Appendix: acronyms, ports and protocols](appendix_acronyms_ports_protocols.md)

## Story scenario catalog

Act and client context are in [World, cast and campaign](../02_world_cast_and_campaign.md).

### Act 1: Onboarding

| Id | Title | Client | Summary | Main objectives |
|----|-------|--------|---------|-----------------|
| S01 | First Night | Lantern | Get a badge (identity proofing), account and MFA enrollment, sign the AUP, tour the building with Walt | 4.6, 1.2, 5.1, 5.6 |
| S02 | Controls Walkthrough | Lantern | Priya points at things around the office and the player names each control's category and type; ends with a gap analysis of Lantern's own lobby | 1.1, 1.2 |
| S03 | The USB in the Parking Lot | Copperline | Found drive, sandbox analysis, hashing, threat feed lookup, removable media policy | 2.2, 2.4, 4.1, 1.4, 4.5 |
| S04 | Lock and Key | Lantern | Set up the player's own workstation: full-disk encryption with TPM, a key pair and certificate for signed email, a password manager | 1.4, 4.6 |
| S05 | Phish Bowl | Lantern, Copperline | Get caught (or not) by Lantern's internal phishing test, then help run Copperline's campaign and fix their email authentication | 5.6, 2.2, 4.5 |
| S06 | Meet the Clients | All | One visit per client: what data they hold, who owns it, who threatens them | 2.1, 3.3, 5.1 |

### Act 2: Hardening season

| Id | Title | Client | Summary | Main objectives |
|----|-------|--------|---------|-----------------|
| S07 | Change Window | Ridgeway | Replace end-of-life servers through the change advisory board: impact analysis, backout plan, maintenance window, dependencies, documentation | 1.3, 4.2 |
| S08 | Zero Trust | Paperkite | Move Paperkite from VPN-and-trust to zero trust: identity provider, SSO, conditional access, policy engine and enforcement points | 1.2, 4.6, 3.2 |
| S09 | Segment the Plant | Brightwater | Separate OT from IT: zones, firewall rules, jump server, data diode decision, IDS on a tap | 3.1, 3.2, 2.5 |
| S10 | Fences and Floodlights | Brightwater | Secure a remote pump station on the floor plan: fence, lighting, bollards, sensors, cameras, lock failure mode | 1.2, 3.2, 2.4 |
| S11 | Phones in Pockets | Copperline | MDM rollout with BYOD/COPE/CYOD, wireless site survey, WPA3-Enterprise with RADIUS | 4.1, 3.2 |
| S12 | Infrastructure as Code | Paperkite | Templates, guard rails, CI pipeline checks, containers, serverless, secrets, code signing | 3.1, 4.7, 4.1 |
| S13 | Count Everything | Harbor | Inventory every device including infusion pumps and the MRI workstation; find end-of-life and unpatchable systems | 4.2, 2.3, 3.1 |
| S14 | Baseline | Lantern lab, all | Build and deploy secure baselines for each hardening target; check them with SCAP benchmarks | 4.1, 4.4, 2.5 |
| S15 | Spray and Pray | Paperkite | An unskilled attacker sprays passwords; tune lockout, add MFA, read the indicators | 2.4, 4.6, 2.1 |

### Act 3: Glasshouse

| Id | Title | Client | Summary | Main objectives |
|----|-------|--------|---------|-----------------|
| S16 | Quiet Vendor | Harbor | The imaging vendor's remote access tool is the way in | 2.2, 3.2, 5.3 |
| S17 | Alerts at 3 a.m. | Harbor | SIEM lights up: read the indicators, correlate, escalate | 2.4, 4.4 |
| S18 | Contain | Harbor | Isolate hosts and segments, decide whether to take the EHR offline during clinic hours | 4.8, 2.5 |
| S19 | Follow the Packets | Harbor | Packet capture and NetFlow show C2 beaconing and exfiltration | 4.9, 2.4 |
| S20 | Double Extortion | Harbor | Ransom note, leak threat, legal counsel, breach notification, law enforcement | 2.1, 5.4, 5.1 |
| S21 | Evidence | Harbor | Order of volatility, imaging, hashing, chain of custody, legal hold | 4.8 |
| S22 | Restore | Harbor | Restore from backups, test RPO and RTO, move imaging to a warm site | 3.4, 5.2 |
| S23 | Root Cause | Harbor, Lantern | Root cause analysis, lessons learned, update the IR plan and training | 4.8, 5.1 |
| S24 | Strange Hours | Copperline | UBA flags an admin's after-hours activity and impossible travel; DLP catches a file leaving | 2.1, 4.5, 2.4 |

### Act 4: Audit season

| Id | Title | Client | Summary | Main objectives |
|----|-------|--------|---------|-----------------|
| S25 | The Examiner | Copperline | Regulator examination: evidence, findings, consequences of non-compliance | 5.4, 5.5 |
| S26 | Trust Services | Paperkite | SOC 2 audit: attestation, control evidence, privacy obligations to EU customers | 5.5, 5.4, 3.3 |
| S27 | We Are the Vendor | Lantern | Copperline assesses Lantern as a third party: questionnaire, right-to-audit, agreements | 5.3 |
| S28 | Scan, Score, Fix | All | Build the vulnerability management program: scan, confirm, prioritize, remediate, validate, report | 4.3 |
| S29 | Rules of Engagement | Ridgeway | Scoped penetration test with Jules: recon, web app findings, privilege escalation in the range | 5.5, 2.3, 2.4 |
| S30 | Risk Register | Lantern | With Marcus: identify, analyze (SLE, ARO, ALE), choose strategies, set appetite and thresholds | 5.2 |
| S31 | The Case Against Dale | Copperline | Insider investigation to completion: forensics, e-discovery, offboarding, PAM gaps | 4.8, 4.6, 5.1 |
| S32 | Policy Rewrite | Ridgeway | Governance structures, policies vs standards vs procedures, roles for data | 5.1 |
| S33 | Crypto Agility | Copperline | Certificate outage, PKI renewal, HSM, weak ciphers and a downgrade attempt | 1.4, 2.3, 2.4 |

### Act 5: Tidewater

| Id | Title | Client | Summary | Main objectives |
|----|-------|--------|---------|-----------------|
| S34 | Poisoned Update | Brightwater | A SCADA vendor's signed update carries a backdoor | 2.2, 2.3, 4.1 |
| S35 | Living Off the Land | Brightwater | Threat hunt with no malware alerts: built-in tools, odd logins, missing logs | 4.8, 4.9, 2.4 |
| S36 | Cover Fire | Brightwater | Hacktivist DDoS and DNS attack on the utility's public site as cover | 2.4, 3.4, 4.5 |
| S37 | Night Visit | Brightwater | Physical intrusion at a pump station: cloned badge, cut fence, environmental tampering | 2.4, 1.2 |
| S38 | Hold the Line | Brightwater | Run the plant through the attack: fail-safe modes, manual operation, continuity of operations, power | 3.4, 3.2 |
| S39 | Share and Report | Brightwater, Lantern | Information sharing, government reporting, threat intel feeds | 4.3, 5.4 |
| S40 | After Action | All | Board briefing, final tabletop, risk appetite; ending depends on the campaign | 5.2, 4.8, 5.1 |

## Side ticket templates

Side tickets are short (2 to 6 beats), repeatable, and generated with random parameters (client, host, user, attacker). They are the main content of Free Shift mode and of remedial practice for leeches.

| Id | Ticket | Main objectives |
|----|--------|-----------------|
| T01 | Triage a reported phish | 2.2, 5.6, 4.5 |
| T02 | Account unlock: verify the caller before you reset | 4.6, 2.2 |
| T03 | Onboard a new hire (accounts, groups, least privilege) | 4.6, 5.1 |
| T04 | Offboard a leaver (disable, revoke, recover assets) | 4.6, 4.2 |
| T05 | Firewall change request | 4.5, 1.3 |
| T06 | Certificate about to expire | 1.4 |
| T07 | Decommission and dispose of a device | 4.2 |
| T08 | Tune a noisy alert | 4.4 |
| T09 | Visitor without a badge | 1.2, 5.6 |
| T10 | Vendor security questionnaire | 5.3 |
| T11 | Vulnerability exception request | 4.3, 5.2 |
| T12 | Investigate an impossible-travel alert | 2.4, 4.9 |
| T13 | Backup restore test | 3.4 |
| T14 | Shadow IT discovery | 2.1, 4.2 |
| T15 | Data subject request (access or erasure) | 5.4 |
| T16 | Classify and label a file share | 3.3 |
| T17 | Write a playbook for a common alert | 4.7, 5.1 |
| T18 | Harden a new device type | 4.1, 2.5 |
| T19 | Review a pull request with a security flaw | 4.1, 2.3 |
| T20 | Quick tabletop: "what if…" | 4.8, 3.4 |
