# (ISC)² CISSP Common Body of Knowledge (aggregated)

**Source BoK:** the ISC2 CISSP CBK (Official ISC2 CISSP CBK Reference) and the CISSP Exam Outline (current outline effective **April 15, 2024**).
**Why aggregated:** the CBK reference book is paid. The exam outline is free but is only a list of headings. Free NIST and CyBOK material covers every topic in depth; this file attaches the best free source to each subdomain.
**Gov tie:** G1 through DoD 8140. CISSP is an approved qualification for many DoD cyber work roles under DoD Manual 8140.03 (and was a top IAT/IAM III cert under the old DoD 8570.01-M). It is also widely required in federal contracts.

Exam outline: [ISC2 CISSP exam outline](https://www.isc2.org/certifications/cissp/cissp-certification-exam-outline) (free).

## Domain weights (2024 outline)

| # | Domain | Weight |
|---|---|---|
| 1 | Security and Risk Management | 16% |
| 2 | Asset Security | 10% |
| 3 | Security Architecture and Engineering | 13% |
| 4 | Communication and Network Security | 13% |
| 5 | Identity and Access Management (IAM) | 13% |
| 6 | Security Assessment and Testing | 12% |
| 7 | Security Operations | 13% |
| 8 | Software Development Security | 10% |

## 1. Security and Risk Management

| Topic | Key content | Best free sources |
|---|---|---|
| Professional ethics | ISC2 Code of Ethics canons; organizational ethics. | [ISC2 Code of Ethics](https://www.isc2.org/ethics) |
| Security concepts | CIA, authenticity, non-repudiation; 5 pillars of IA. | [CNSSI 4009 glossary](https://www.cnss.gov/); [NIST glossary](https://csrc.nist.gov/glossary) |
| Governance | Alignment to business, org processes (M&A, divestiture), roles, frameworks (CSF, 800-53, ISO 27001, COBIT), due care / due diligence. | [CSF 2.0 Govern](https://www.nist.gov/cyberframework); [cobit.md](cobit.md); [iso-iec-27001-27002.md](iso-iec-27001-27002.md) |
| Legal & regulatory | Cybercrime, licensing, IP, import/export (ITAR, EAR, Wassenaar), transborder data flow, privacy (GDPR, HIPAA, GLBA, Privacy Act), contractual/legal/industry standards (PCI DSS, SOX). | [CyBOK Law & Regulation KA](https://www.cybok.org/); [FPC FIPPs](https://www.fpc.gov/resources/fipps/) |
| Investigations | Administrative, criminal, civil, regulatory, industry standards. | [NIST SP 800-86 forensics](https://csrc.nist.gov/pubs/sp/800/86/final) |
| Policies, standards, procedures, guidelines | Document hierarchy. | 800-53 "-1" controls |
| BCP / BIA | Business impact analysis, RTO/RPO/MTD, external dependencies. | [NIST SP 800-34](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final) |
| Personnel security | Screening, agreements, onboarding/offboarding, vendor/consultant controls. | 800-53 PS family |
| Risk management | Identification, assessment (quantitative: SLE = AV × EF, ALE = SLE × ARO), response, countermeasure selection, control types (preventive, detective, corrective, deterrent, recovery, compensating, directive), control assessments, monitoring, frameworks (RMF, ISO 31000, COSO, ISACA). | [SP 800-30r1](https://csrc.nist.gov/pubs/sp/800/30/r1/final); [SP 800-37r2](https://csrc.nist.gov/pubs/sp/800/37/r2/final); [SP 800-39](https://csrc.nist.gov/pubs/sp/800/39/final) |
| Threat modeling | STRIDE, PASTA, attack trees, DREAD. | [CISA/OWASP threat modeling](https://owasp.org/www-community/Threat_Modeling); [CAPEC](https://capec.mitre.org/) |
| Supply chain risk management | Hardware/software/services risks, third-party assessment, minimum requirements, SLAs. | [SP 800-161r1](https://csrc.nist.gov/pubs/sp/800/161/r1/upd1/final) |
| Awareness, education, training | Methods, periodic content review, effectiveness. | [SP 800-50r1](https://csrc.nist.gov/pubs/sp/800/50/r1/final) |

## 2. Asset Security

| Topic | Best free sources |
|---|---|
| Information and asset classification; handling requirements | [CUI Registry](https://www.archives.gov/cui); FIPS 199; [SP 800-60](https://csrc.nist.gov/pubs/sp/800/60/v1/r1/final) |
| Provisioning, inventory, asset lifecycle | [NIST SP 1800-5](https://www.nccoe.nist.gov/); 800-53 CM-8 |
| Data roles (owner, controller, custodian, processor, user, subject) | [NIST Privacy Framework](https://www.nist.gov/privacy-framework) |
| Data lifecycle, remanence, retention | [SP 800-88r2 media sanitization](https://csrc.nist.gov/pubs/sp/800/88/r2/final); NARA |
| Data security controls, states of data (rest, transit, use), scoping & tailoring, DRM, DLP, CASB | 800-53 SC, MP families; [dama-dmbok.md](dama-dmbok.md) |

## 3. Security Architecture and Engineering

| Topic | Best free sources |
|---|---|
| Secure design principles: threat modeling, least privilege, defense in depth, secure defaults, fail securely, SoD, KISS, zero trust, privacy by design, trust but verify, shared responsibility | [SP 800-160 v1r1 Appendix E (design principles)](https://csrc.nist.gov/pubs/sp/800/160/v1/r1/final); [SP 800-207 zero trust](https://csrc.nist.gov/pubs/sp/800/207/final) |
| Security models: Bell-LaPadula, Biba, Clark-Wilson, Brewer-Nash, Graham-Denning, Harrison-Ruzzo-Ullman, state machine, information flow | [CyBOK Operating Systems & Virtualisation and Authentication, Authorisation & Accountability KAs](https://www.cybok.org/) |
| Evaluation criteria: Common Criteria (EAL, PP), TCSEC/ITSEC history | [Common Criteria portal](https://www.commoncriteriaportal.org/) (free CC parts); [NIAP](https://www.niap-ccevs.org/) (US scheme) |
| Capabilities: TPM, HSM, memory protection, TEE | [NIST SP 800-193 platform resiliency](https://csrc.nist.gov/pubs/sp/800/193/final) |
| Vulnerabilities by architecture: client, server, database, crypto, ICS/SCADA, cloud (SaaS/PaaS/IaaS), distributed, IoT, microservices, containers, serverless, embedded, HPC, edge, virtualized | [SP 800-82r3 OT](https://csrc.nist.gov/pubs/sp/800/82/r3/final); [SP 800-190 containers](https://csrc.nist.gov/pubs/sp/800/190/final); [SP 800-145/146 cloud](https://csrc.nist.gov/pubs/sp/800/145/final) |
| Cryptography: lifecycle, methods (symmetric, asymmetric, ECC, quantum), PKI, key management, digital signatures, non-repudiation, integrity (hashing) | [SP 800-57 key management](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final); [SP 800-175B](https://csrc.nist.gov/pubs/sp/800/175/b/r1/final); [FIPS 203/204/205 post-quantum](https://csrc.nist.gov/projects/post-quantum-cryptography); [CyBOK Applied Cryptography KA](https://www.cybok.org/) |
| Cryptanalytic attacks: brute force, ciphertext-only, known/chosen plaintext, frequency analysis, implementation, side-channel, fault injection, timing, MITM, pass the hash, Kerberos exploitation, ransomware | [CyBOK Hardware Security KA](https://www.cybok.org/); [MITRE ATT&CK](https://attack.mitre.org/) |
| Site & facility design and controls: wiring closets, server rooms, media storage, evidence storage, restricted areas, utilities/HVAC, environmental, fire, power | 800-53 PE family; [Interagency Security Committee (ISC) standards](https://www.cisa.gov/topics/physical-security/interagency-security-committee) |
| Information system lifecycle | [life cycle file](iso-iec-ieee-12207-and-15288-life-cycle-processes.md) |

## 4. Communication and Network Security

| Topic | Best free sources |
|---|---|
| OSI/TCP-IP, IPv4/IPv6, secure protocols (IPsec, SSH, TLS), multilayer protocols, converged (iSCSI, VoIP, InfiniBand), micro-segmentation, wireless (Wi-Fi, Zigbee, satellite), cellular (4G/5G), CDNs, SDN/SD-WAN, VPC, monitoring | [SP 800-77r1 IPsec](https://csrc.nist.gov/pubs/sp/800/77/r1/final); [SP 800-52r2 TLS](https://csrc.nist.gov/pubs/sp/800/52/r2/final); [SP 800-153 WLAN](https://csrc.nist.gov/pubs/sp/800/153/final); [SP 800-187 LTE](https://csrc.nist.gov/pubs/sp/800/187/final); [CyBOK Network Security KA](https://www.cybok.org/) |
| Secure network components: operation of infrastructure, transmission media, NAC, endpoint security | [SP 800-41r1 firewalls](https://csrc.nist.gov/pubs/sp/800/41/r1/final); [DISA network STIGs](https://public.cyber.mil/stigs/) |
| Secure communication channels: voice/video/collab, remote access, data communications, third-party connectivity | [SP 800-46r2 telework](https://csrc.nist.gov/pubs/sp/800/46/r2/final); [CISA TIC 3.0](https://www.cisa.gov/resources-tools/programs/trusted-internet-connections-tic) |

## 5. Identity and Access Management

| Topic | Best free sources |
|---|---|
| Physical and logical access to assets | 800-53 AC, PE |
| Identification & authentication: IdM, single/multi-factor, accountability, session management, registration/proofing, federated identity, credential management, SSO, JIT | [SP 800-63-4 Digital Identity Guidelines](https://pages.nist.gov/800-63-4/); [FIPS 201-3 PIV](https://csrc.nist.gov/pubs/fips/201-3/final); [IDManagement.gov (FICAM)](https://www.idmanagement.gov/) |
| Federated identity with third-party services | FICAM architecture; SAML/OIDC specs |
| Authorization mechanisms: RBAC, rule-based, MAC, DAC, ABAC, risk-based, access policy enforcement (PDP/PEP) | [SP 800-162 ABAC](https://csrc.nist.gov/pubs/sp/800/162/upd2/final); [NIST RBAC project](https://csrc.nist.gov/projects/role-based-access-control) |
| Identity and access provisioning lifecycle: account access review, provisioning/deprovisioning, role definition and transition, privilege escalation (sudo, monitoring) | 800-53 AC-2, AC-6 |
| Authentication systems: OIDC/OAuth, SAML, Kerberos, RADIUS/TACACS+ | [CyBOK AAA KA](https://www.cybok.org/) |

## 6. Security Assessment and Testing

| Topic | Best free sources |
|---|---|
| Assessment, test, audit strategies (internal, external, third-party; location) | [SP 800-53A](https://csrc.nist.gov/pubs/sp/800/53/a/r5/final); [SP 800-115](https://csrc.nist.gov/pubs/sp/800/115/final); [GAO FISCAM](https://www.gao.gov/fiscam) |
| Security control testing: vulnerability assessment, penetration testing (red, blue, purple), log reviews, synthetic transactions, code review/testing, misuse case testing, coverage analysis, interface testing, breach attack simulation, compliance checks | SP 800-115; [OWASP WSTG](https://owasp.org/www-project-web-security-testing-guide/); [CISA assessments](https://www.cisa.gov/resources-tools/services) |
| Collect security process data: account management, management review, KPIs/KRIs, backup verification, training/awareness, DR/BC | [SP 800-55](https://csrc.nist.gov/pubs/sp/800/55/v1/final); [SP 800-137](https://csrc.nist.gov/pubs/sp/800/137/final) |
| Analyze output and report: remediation, exception handling, ethical disclosure | [CISA Coordinated Vulnerability Disclosure](https://www.cisa.gov/coordinated-vulnerability-disclosure-process); [BOD 20-01 VDP](https://www.cisa.gov/news-events/directives/bod-20-01-develop-and-publish-vulnerability-disclosure-policy) |
| Conduct or facilitate audits (internal, external, third-party; SOC reports) | [GAO Yellow Book](https://www.gao.gov/yellowbook) |

## 7. Security Operations

| Topic | Best free sources |
|---|---|
| Investigations: evidence collection and handling, reporting, techniques, digital forensics tools, artifacts | [SP 800-86](https://csrc.nist.gov/pubs/sp/800/86/final); [SWGDE documents](https://www.swgde.org/documents/published-complete-listing/) |
| Logging and monitoring: IDS/IPS, SIEM, SOAR, continuous monitoring, egress monitoring, log management, threat intelligence, UEBA | [SP 800-92](https://csrc.nist.gov/pubs/sp/800/92/r1/ipd); [SP 800-94 IDPS](https://csrc.nist.gov/pubs/sp/800/94/final); [OMB M-21-31 logging maturity](https://www.whitehouse.gov/omb/information-resources/guidance/) |
| Configuration management: provisioning, baselining, automation | [SP 800-128](https://csrc.nist.gov/pubs/sp/800/128/upd1/final); DISA STIGs; CIS Benchmarks |
| Foundational security operations concepts: need-to-know/least privilege, SoD, privileged account mgmt, job rotation, SLAs | 800-53 AC-5, AC-6 |
| Resource protection: media management, media protection techniques, data at rest/in transit | 800-53 MP; SP 800-111 |
| Incident management: detection, response, mitigation, reporting, recovery, remediation, lessons learned | [SP 800-61r3](https://csrc.nist.gov/pubs/sp/800/61/r3/final); [CISA playbooks](https://www.cisa.gov/resources-tools/resources/federal-government-cybersecurity-incident-and-vulnerability-response-playbooks) |
| Detective and preventive measures: firewalls, IDS/IPS, whitelisting/blacklisting, third-party services, sandboxing, honeypots, anti-malware, ML/AI tools | [SP 800-83 malware](https://csrc.nist.gov/pubs/sp/800/83/r1/final); [SP 800-167 application allowlisting](https://csrc.nist.gov/pubs/sp/800/167/final) |
| Patch and vulnerability management | [SP 800-40r4](https://csrc.nist.gov/pubs/sp/800/40/r4/final); [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) |
| Change management | ITIL change enablement ([itil-4.md](itil-4.md)); 800-53 CM-3 |
| Recovery strategies: backup storage, recovery sites (hot/warm/cold/cloud), resilience, HA, QoS, fault tolerance | [SP 800-34](https://csrc.nist.gov/pubs/sp/800/34/r1/upd1/final); [SP 800-209 storage](https://csrc.nist.gov/pubs/sp/800/209/final) |
| DR processes: response, personnel, communications, assessment, restoration, training; DR plan testing (read-through, walkthrough, simulation, parallel, full interruption) | [SP 800-84 TT&E](https://csrc.nist.gov/pubs/sp/800/84/final); [CISA Tabletop Exercise Packages](https://www.cisa.gov/resources-tools/services/cisa-tabletop-exercise-packages) |
| Business continuity planning and exercises | [FEMA continuity](https://www.fema.gov/emergency-managers/national-preparedness/continuity) |
| Physical security: perimeter, internal | ISC standards |
| Personnel safety and security: travel, training, emergency management, duress | |

## 8. Software Development Security

| Topic | Best free sources |
|---|---|
| Security in the SDLC: methodologies (Agile, Waterfall, DevOps, DevSecOps, Scaled Agile), maturity models (CMM, SAMM), operation and maintenance, change management, IPT | [SSDF SP 800-218](https://csrc.nist.gov/pubs/sp/800/218/final); [OWASP SAMM](https://owaspsamm.org/); [DoD DevSecOps Fundamentals](https://dodcio.defense.gov/Portals/0/Documents/Library/DoD%20Enterprise%20DevSecOps%20Fundamentals%20v2.5.pdf); [cmmi.md](cmmi.md) |
| Security controls in software development ecosystems: languages, libraries, tool sets, IDE, runtime, CI/CD, SOAR, SCM, code repositories, application security testing (SAST, DAST, IAST, SCA, fuzzing) | [CISA Secure by Design](https://www.cisa.gov/securebydesign); [NIST SP 800-204D (DevSecOps supply chain)](https://csrc.nist.gov/pubs/sp/800/204/d/final); [CISA SBOM resources](https://www.cisa.gov/sbom) |
| Assess effectiveness of software security: auditing and logging of changes, risk analysis and mitigation | [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) |
| Assess security impact of acquired software: COTS, open source, third-party, managed services (SaaS/IaaS/PaaS) | [CISA Secure Software Attestation](https://www.cisa.gov/secure-software-attestation-form); [SP 800-161r1](https://csrc.nist.gov/pubs/sp/800/161/r1/upd1/final) |
| Secure coding guidelines and standards: weaknesses at source-code level, API security, secure coding practices, software-defined security | [SEI CERT standards](https://wiki.sei.cmu.edu/confluence/display/seccode); [CWE Top 25](https://cwe.mitre.org/top25/); [OWASP Cheat Sheets](https://cheatsheetseries.owasp.org/); [OWASP API Security Top 10](https://owasp.org/www-project-api-security/) |

## Free study companions

- [CyBOK](https://www.cybok.org/) as the academic deep dive behind every domain (CyBOK publishes a mapping of its KAs to certifications).
- [NICE Framework](https://www.nist.gov/itl/applied-cybersecurity/nice/nice-framework-resource-center) to see which work roles each domain serves.
- [CISA free training (FedVTE successor courses)](https://www.cisa.gov/resources-tools/training) for structured coursework.
