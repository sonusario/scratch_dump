# 2. World, cast and campaign

All organizations, people and threat groups here are fictional.

## Why a managed security provider

Security+ spans policy, architecture, operations, physical security and compliance across very different kinds of organization. A single company cannot plausibly need HIPAA, PCI DSS, SCADA, serverless and records retention all at once. A **managed security service provider (MSSP)** can, because it serves several clients. It also lets the game teach third-party risk from both sides, since the player's employer *is* a third party to every client.

## Lantern Security (the hub)

A 30-person MSSP in a converted warehouse. The player starts as a junior analyst on the night shift.

| Location | Used for |
|----------|----------|
| SOC floor | The alert queue, SIEM wall, ticketing, shift handoffs. The player's desk is here and it is where most daily reviews start. |
| Lab | Building and testing baselines, sandboxing malware, test VMs for patches, a practice range for authorized penetration tests |
| Server room | Lantern's own infrastructure: SIEM cluster, log storage, backup appliance, HSM for client key custody |
| Conference room | Tabletop exercises, change advisory board (CAB) meetings, vendor reviews, audit interviews |
| Lobby and loading dock | Visitor management, badges, deliveries, tailgating and pretexting scenarios |
| Records closet and shred bin | Data retention, destruction, chain of custody storage, legal hold |
| Rooftop and parking lot | Wireless site surveys, physical perimeter (lighting, cameras, fence) |

## The five clients

Each client exists to carry a cluster of concepts. Every client site is a small explorable map plus several computers.

| Client | What they are | Concepts they carry | Compliance flavor |
|--------|---------------|---------------------|-------------------|
| **Harbor Street Clinic** | Three-building outpatient clinic with an imaging suite | Ransomware, medical IoT and embedded devices, legacy and end-of-life systems, privacy and data classification, backups and recovery, availability, physical security of patient areas | HIPAA, breach notification, data subjects |
| **Copperline Credit Union** | Four branches, a call center and an online banking platform | Fraud and BEC, vishing, MFA and IAM, cryptography and PKI, HSMs, tokenization, insider threat, segregation of duties, quantitative risk | PCI DSS, GLBA, regulator examinations |
| **Brightwater Municipal Water** | Treatment plant plus remote pump stations | ICS/SCADA, RTOS, air gaps and segmentation, nation-state actors, hacktivists, physical security (fences, bollards, sensors, lighting), power and generators, environmental attacks | NIST CSF, CISA advisories, government reporting |
| **Paperkite** | A 40-person software startup that is all cloud | IaC, containers, serverless, microservices, CI/CD and automation, SDLC and code review, secrets, shadow IT, bug bounty, SaaS sprawl, multi-cloud | SOC 2, GDPR (EU customers), data sovereignty |
| **Ridgeway County Records Office** | County government office handling land, court and election records | Legacy systems, records retention and destruction, legal hold and e-discovery, public kiosks, governance structures, change management, data sovereignty in government cloud | State and federal government requirements (FISMA-style controls, NIST SP 800-53 flavor), public records law |

## Cast

| Character | Role | Teaching job |
|-----------|------|--------------|
| **Priya Raman** | SOC lead, the player's mentor | Explains, assigns, reviews the player's work. Her voice delivers most "Again" runbook explanations. |
| **Marcus Hale** | Lantern's CISO | Governance, risk appetite, board meetings, policy |
| **Jules Okafor** | Contract penetration tester | Rules of engagement, recon, known/unknown environment tests, how attacks look from the other side |
| **Inés Vargas** | External auditor (recurring across clients) | Audits, attestation, evidence, findings, right-to-audit |
| **Walt Brennan** | Lantern's facilities and security guard | Physical security, visitor logs, badge systems, cameras |
| **Theo Lindqvist** | Lantern sysadmin, slightly careless | Change management mistakes, misconfigurations, default credentials. Not malicious. |
| **Rosa Delgado** | Harbor Clinic practice manager | Privacy, availability pressure ("the doctors need the system now") |
| **Femi Adeyemi** | Copperline IT manager | IAM, PAM, cryptography projects |
| **Hank Sorensen** | Brightwater plant operator, 30 years in | OT vs IT culture, why you cannot just patch a PLC |
| **Mei Tanaka** | Paperkite CTO | Speed vs security trade-offs, automation, cloud architecture |
| **Gloria Banks** | Ridgeway County Clerk | Governance, retention law, public trust |

### Threat actors (one per actor type in objective 2.1)

| Group | Actor type | Motivation | Where they appear |
|-------|------------|------------|-------------------|
| **Tidewater** | Nation-state | Espionage, pre-positioning for war-time disruption | Brightwater, Act 5 |
| **Glasshouse** | Organized crime | Financial gain through ransomware and blackmail (double extortion) | Harbor Clinic, Act 3 |
| **Open Valve** | Hacktivist | Political belief (opposes a water rate increase) | Brightwater website defacement, DDoS |
| **"zer0cool_17"** | Unskilled attacker | Bragging rights, chaos | Paperkite login spraying with a bought kit |
| **Dale Pruitt** | Insider threat | Revenge after being passed over, then financial gain | Copperline, Acts 2 to 4 |
| **Paperkite marketing team** | Shadow IT | Convenience | Unsanctioned SaaS with customer data |

## Campaign structure

The campaign is about 40 **shifts** in five acts. A shift is one play session's worth of story (10 to 25 minutes) plus the due-review chores (see [core loop](03_core_loop_and_beats.md)). Acts emphasize domains but never only one, because real incidents cross domains.

| Act | Title | Shifts | Main domains | Arc |
|-----|-------|--------|--------------|-----|
| 1 | **Onboarding** | 1 to 6 | 1, 5.6, 4.6 | The player gets a badge, an account and MFA, signs the AUP, sits awareness training (and gets phished by the internal test), shadows Priya, meets each client, and learns controls, CIA, AAA and the basics of crypto while setting up their own workstation. |
| 2 | **Hardening season** | 7 to 15 | 3, 4.1, 2.5, 1.3, 4.2 | Each client gets a project: segment Brightwater's OT network, roll out MDM at Copperline, move Paperkite to IaC with guard rails, replace Ridgeway's end-of-life servers through a proper change process, inventory Harbor's medical devices. Small attacks probe throughout (spraying, a malicious USB). |
| 3 | **Glasshouse** | 16 to 24 | 2.4, 4.8, 4.9, 3.4, 4.4 | Ransomware hits Harbor Clinic through a vendor's remote access. The player detects, contains, investigates, preserves evidence, restores from backups, runs the post-incident review and learns which backups were never tested. Copperline's insider is noticed by UBA but not yet proven. |
| 4 | **Audit season** | 25 to 33 | 5, 4.3, 4.5 | Copperline's regulator exam, Paperkite's SOC 2, a third-party review of Lantern itself (the player is the vendor now), a vulnerability management program overhaul, a scoped penetration test with Jules. The insider case closes with forensics and legal hold. |
| 5 | **Tidewater** | 34 to 40 | All | A nation-state campaign against Brightwater uses everything: supply chain compromise of a SCADA vendor update, living-off-the-land, a physical intrusion at a pump station, and a DDoS by Open Valve as cover. The player coordinates across all clients, makes risk decisions under pressure, and the ending reflects the choices and controls built over the whole campaign. |

After Act 5 the game opens **Free Shift** mode: endless procedurally assembled tickets drawn from scenario templates, weighted toward the player's weakest objectives, so the game remains a study tool after the story ends.

## Persistent world state

The world remembers what the player built. This is what makes the hardening work in Act 2 matter in Acts 3 and 5.

- **Controls register:** every control the player deploys (a firewall rule, MFA on a group, a camera, a policy) is a record with a type, category, client and location. Later attacks check the register. For example, Glasshouse's lateral movement is stopped at the VLAN boundary if the player segmented Harbor's imaging network in Act 2, and it spreads if they did not.
- **Client trust:** one meter per client. It rises with good outcomes and clear communication, and falls with outages, findings and breaches. It changes dialogue and what clients let the player do (a low-trust client refuses a maintenance window).
- **Risk register:** risks the player identified, with owners and chosen strategies. Accepted risks can come back.
- **Evidence locker:** forensic images, logs and documents with chain-of-custody records. Mishandled evidence matters in the Act 4 insider case.
- **Mastery map:** see [mastery](09_mastery_and_assessment.md).
