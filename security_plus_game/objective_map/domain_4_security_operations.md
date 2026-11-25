# Domain 4: Security Operations (28%)

[Back to the map](README.md)

This is the largest domain, and most of it is hands-on, so it leans hardest on the [in-game computer](../05_virtual_computer.md).

## 4.1 Given a scenario, apply common security techniques to computing resources

**Teaching approach.** S14 builds baselines in the Lantern lab and deploys them across clients. S11 is the mobile and wireless scenario. S12 and T19 cover application security in Paperkite's pipeline. Each hardening target has a T18 ticket variant so every target gets hands-on practice.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Secure baselines: establish | S14 | Pick a benchmark, adapt it, document exceptions | A documented standard configuration for a type of system → Secure baseline |
| Secure baselines: deploy | S14 | Push via GPO and MDM | Baselines are usually deployed with ______ or MDM. → Group Policy / configuration management |
| Secure baselines: maintain | S14, S28 | Config Auditor flags drift; update baseline when vendor guidance changes | Systems drifting from their baseline should be detected by ______. → Configuration/compliance scans |
| Hardening target: mobile devices | S11 | MDM profile: screen lock, encryption, no side loading | A key hardening step for phones → Enforce screen lock and encryption via MDM |
| Workstations | S14 | Baseline GPO | Removing local admin rights on workstations applies ______. → Least privilege |
| Switches | S10, S14 | Disable unused ports, port security, SSH only | Hardening a switch: disable unused ports and replace Telnet with ______. → SSH |
| Routers | S14 | ACLs, disable unused services, SNMPv3 | The SNMP version with authentication and encryption → SNMPv3 |
| Cloud infrastructure | S12 | Guard rails, no public buckets, MFA on root | The first thing to lock down in a new cloud account → The root/owner account (MFA, no daily use) |
| Servers | S14 | Remove roles, host firewall, patch | Servers should run only the ______ they need. → Services |
| ICS/SCADA | S09, S38 | Segmentation, no internet, vendor-approved patches only | ICS hardening relies heavily on network ______ because patching is hard. → Segmentation |
| Embedded systems | S13 | Change defaults, isolate, firmware updates | When embedded devices can't be patched, ______ them. → Isolate/segment |
| RTOS | S38 | Restrict who can program the controller | RTOS devices often can't run security agents, so protect them at the ______. → Network |
| IoT devices | S13 | IoT VLAN, change defaults | IoT devices belong on their own ______. → Network segment/VLAN |
| Wireless: site surveys | S11 | Wireless Planner walk-through of a branch | Measuring a site's wireless signals and interference before installing → Site survey |
| Wireless: heat maps | S11 | Planner output; spot coverage leaking to the parking lot | A visual map of wireless signal strength → Heat map |
| Mobile solutions: mobile device management (MDM) | S11 | MDM Console | A system to manage, secure and wipe mobile devices centrally → MDM |
| Deployment model: bring your own device (BYOD) | S11 | Tellers' own phones with a work container | Employees use their own devices for work → BYOD |
| Corporate-owned, personally enabled (COPE) | S11 | Managers get company phones they may use personally | The company owns the device but allows personal use → COPE |
| Choose your own device (CYOD) | S11 | Pick from an approved list | Employees choose from approved devices the company owns → CYOD |
| Connection methods: cellular | S11 | Phones bypass the corporate network | Data sent over cellular bypasses the company's ______. → Network controls |
| Wi-Fi | S11 | Corporate SSID | Wi-Fi connections should use ______ for enterprise security. → WPA3-Enterprise |
| Bluetooth | S11 | Disable discoverable mode | Bluetooth should be set to non-______ when not pairing. → Discoverable |
| Wireless security settings: Wi-Fi Protected Access 3 (WPA3) | S11 | Choose WPA3; compare to WPA2 | WPA3 replaces the PSK handshake with ______. → SAE (Simultaneous Authentication of Equals) |
| AAA/Remote Authentication Dial-In User Service (RADIUS) | S11 | Set the AP to use the RADIUS server | The protocol APs use to send enterprise Wi-Fi logins to a central server → RADIUS |
| Cryptographic protocols | S11 | WPA3 uses AES-based encryption (GCMP) | WPA2 used CCMP with ______ encryption. → AES |
| Authentication protocols | S11 | EAP-TLS vs PEAP | The EAP method that requires certificates on both client and server → EAP-TLS |
| Application security: input validation | S29, T19 | Fix the SQLi in Code Review | Checking that input matches what is expected before using it → Input validation |
| Secure cookies | T19 | Set Secure, HttpOnly, SameSite | The cookie flag that stops JavaScript from reading it → HttpOnly |
| Static code analysis | S12 | SAST in the CI pipeline | Analyzing source code for flaws without running it → Static analysis (SAST) |
| Code signing | S12, S34 | Sign builds; verify vendor signatures | Signing software so users can verify its author and integrity → Code signing |
| Sandboxing | S03, S12 | Lab sandbox detonation | Running code in an isolated environment → Sandboxing |
| Monitoring | S14 | Add new baselines to monitoring | After hardening, you need ______ to know if settings change. → Monitoring |

## 4.2 Explain the security implications of proper hardware, software, and data asset management

**Teaching approach.** S13 is an inventory hunt at Harbor: walk the clinic, find devices in the world (including ones nobody listed), and reconcile them with the Asset Inventory app. T04 and T07 cover the end of the life cycle with a disposal decision and a certificate of destruction.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Acquisition/procurement process | S07 | Security review before buying the new servers | Security requirements should be set during ______, before buying. → Procurement |
| Assignment/accounting: ownership | S13 | Each asset gets an owner | Every asset needs a named ______ accountable for it. → Owner |
| Assignment/accounting: classification | S13 | Asset classified by the data it holds | Assets are classified by the ______ they hold or support. → Data/criticality |
| Monitoring/asset tracking: inventory | S13 | Asset Inventory app | A complete list of an organization's assets → Inventory |
| Monitoring/asset tracking: enumeration | S13, S28 | Network scan finds the unlisted smart TV | Discovering and listing devices and software on a network → Enumeration |
| Disposal/decommissioning: sanitization | T07 | Wipe a drive (overwrite, crypto erase) | Removing data so it cannot be recovered, allowing reuse → Sanitization |
| Destruction | T07 | Shred the drives from the old records server | Physically destroying media (shredding, pulverizing, incinerating) → Destruction |
| Certification | T07 | Get a certificate of destruction from the vendor | A document proving media was destroyed → Certificate of destruction |
| Data retention | S07, S32 | Ridgeway must keep land records 75 years; some data must be deleted sooner | Rules for how long data must be kept → Data retention |

## 4.3 Explain various activities associated with vulnerability management

**Teaching approach.** S28 is a full program cycle in the Vuln Scanner, from scan to report. T11 (exception request) recurs. S29 and S39 add the pentest and threat-intel sources.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Identification: vulnerability scan | S28 | Run credentialed and non-credentialed scans; compare | A scan that logs into hosts to check them in depth → Credentialed scan |
| Application security: static analysis | S12 | SAST results | Finding flaws in code without running it → Static analysis |
| Dynamic analysis | S29 | DAST against the Ridgeway portal | Testing a running application for flaws → Dynamic analysis |
| Package monitoring | S12 | Dependency monitor flags a vulnerable library | Tracking third-party libraries for known vulnerabilities → Package monitoring |
| Threat feed: open-source intelligence (OSINT) | S29, S39 | Public advisories, forums | Intelligence gathered from public sources → OSINT |
| Proprietary/third-party | S39 | Paid feed in the SIEM | A commercial threat feed is ______. → Proprietary/third-party |
| Information-sharing organization | S39 | Join the water sector ISAC | A sector group that shares threat information among members → Information-sharing organization (ISAC) |
| Dark web | S20 | Glasshouse leak site lists Harbor | Monitoring criminal forums for your leaked data uses the ______. → Dark web |
| Penetration testing | S29 | Scoped test with Jules | An authorized simulated attack to find exploitable weaknesses → Penetration test |
| Responsible disclosure program | S29 | Researcher reports a Ridgeway bug through the published process | A published process for outsiders to report vulnerabilities → Responsible disclosure program |
| Bug bounty program | S12 | Paperkite launches one | Paying outside researchers for valid vulnerability reports → Bug bounty |
| System/process audit | S26 | Audit finds unpatched systems | Reviewing systems and processes against requirements to find weaknesses → Audit |
| Analysis: confirmation | S28 | Verify a finding manually | Before fixing, a scan finding should be ______. → Confirmed |
| False positive | S28 | Scanner flags a patched version | A finding reported that does not actually exist → False positive |
| False negative | S28 | Scanner missed a real hole Jules found | A real vulnerability the scan failed to report → False negative |
| Prioritize | S28 | Order the backlog | Remediation is ordered by risk: severity, exposure and ______. → Asset criticality |
| Common Vulnerability Scoring System (CVSS) | S28 | Read and adjust scores | A standard 0–10 score for vulnerability severity → CVSS |
| Common Vulnerabilities and Exposures (CVE) | S28 | Each finding has a CVE id | A public list of unique identifiers for known vulnerabilities → CVE |
| Vulnerability classification | S28 | Tag findings by type | Grouping vulnerabilities by type (e.g., injection, misconfiguration) → Classification |
| Exposure factor | S28, S30 | How much of the asset's value is at risk | The percentage of an asset's value lost in an incident → Exposure factor |
| Environmental variables | S28 | Same CVE scored differently on an air-gapped host | CVSS environmental metrics adjust a score for your ______. → Specific environment |
| Industry/organizational impact | S28 | A clinic outage is worse than a startup's | The same flaw can matter more in healthcare because of ______. → Patient safety/regulatory impact |
| Risk tolerance | S28 | Medium findings allowed 90 days | How much risk an organization will accept for a specific item → Risk tolerance |
| Response: patching | S28 | Patch | The most common remediation → Patching |
| Insurance | S30 | Cyber insurance as transfer | Buying cyber insurance is risk ______. → Transfer |
| Segmentation | S13 | Isolate unpatchable hosts | Remediating an unpatchable device by isolating it → Segmentation |
| Compensating controls | S13 | WAF in front of an unpatched app | A WAF protecting an app that can't be patched yet is a ______ control. → Compensating |
| Exceptions and exemptions | T11 | Approve with expiry and owner | A formally approved, time-limited acceptance of a known vulnerability → Exception |
| Validation: rescanning | S28 | Rescan to confirm | After patching, confirm the fix with a ______. → Rescan |
| Validation: audit | S28 | Spot-check remediation records | Reviewing records to confirm remediation actually happened → Audit |
| Validation: verification | S28 | Manually confirm the fix | Directly checking that a fix works → Verification |
| Reporting | S28 | Monthly report to Marcus in Docs | Communicating vulnerability status and trends to leadership → Reporting |

## 4.4 Explain security alerting and monitoring concepts and tools

**Teaching approach.** The SOC alert queue in the SIEM is the backbone of the night shift. S17 introduces it; T08 tuning tickets recur. The player places agents, configures log sources, and writes and tunes correlation rules.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Monitoring computing resources: systems | S14 | Server agents | Watching OS events, CPU and logins on servers → System monitoring |
| Applications | S17 | App logs into SIEM | Watching an app's logs and errors → Application monitoring |
| Infrastructure | S17 | Network devices via syslog/SNMP | Watching routers, switches and firewalls → Infrastructure monitoring |
| Activity: log aggregation | S17 | Add sources to the SIEM | Collecting logs from many sources into one place → Log aggregation |
| Alerting | S17 | Write a rule that alerts | Notifying analysts when a rule matches → Alerting |
| Scanning | S28 | Scheduled scans feed the SIEM | Regularly checking systems for vulnerabilities and misconfigurations → Scanning |
| Reporting | S28 | Dashboards and weekly report | Summarizing monitoring data for decision-makers → Reporting |
| Archiving | S21 | Retain logs per policy for investigations | Storing older logs long-term for compliance and investigations → Archiving |
| Alert response and remediation/validation: quarantine | S17 | Quarantine from EDR | Moving a suspicious file or host where it can do no harm → Quarantine |
| Alert tuning | T08 | Reduce false positives without hiding true positives | Adjusting rules to reduce false positives → Alert tuning |
| Tools: Security Content Automation Protocol (SCAP) | S14 | Config Auditor imports SCAP content | A set of standards for automating configuration and vulnerability checks → SCAP |
| Benchmarks | S14 | CIS-style benchmark | Published best-practice configuration guides → Benchmarks |
| Agents/agentless | S14, S28 | Agent on servers; agentless for PLCs | Monitoring without installing software on the host → Agentless |
| Security information and event management (SIEM) | S17 | Beacon app | A system that collects, correlates and alerts on security logs → SIEM |
| Antivirus | S03 | Signature detection on the sandbox | Software that detects known malware, mainly by signatures → Antivirus |
| Data loss prevention (DLP) | S24 | DLP blocks Dale's upload | Tools that detect and stop sensitive data leaving → DLP |
| Simple Network Management Protocol (SNMP) traps | S17 | Switch sends a trap when a port goes down | An alert a device sends to a manager without being asked → SNMP trap |
| NetFlow | S19 | Flow Viewer | Metadata about network traffic flows (who, where, how much) → NetFlow |
| Vulnerability scanners | S28 | Sounding app | Tools that check systems for known vulnerabilities → Vulnerability scanners |

## 4.5 Given a scenario, modify enterprise capabilities to enhance security

**Teaching approach.** Hands-on in the Firewall Manager, IDS/IPS Console, Directory Admin (GPO), DNS records, EDR Console, and DLP. Each concept has at least one checked computer task.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Firewall: rules | S09, T05 | Write and order rules; implicit deny at the end | Firewall rules are processed top-down and end with an implicit ______. → Deny |
| Access lists | S09 | Router ACLs | Rules on a router permitting or denying traffic → Access lists |
| Ports/protocols | T05 | Allow 443, block 23 | Which port should be blocked to stop Telnet? → 23 |
| Screened subnets | S36 | Put the public web server in the screened subnet | A network segment between the internet and internal network for public-facing servers → Screened subnet (DMZ) |
| IDS/IPS: trends | S17 | Trend dashboard shows rising scans | Watching alert volumes over time helps spot ______. → Emerging attacks |
| Signatures | S17 | Add a signature for Glasshouse's C2 | Detection based on known patterns of attacks → Signature-based |
| Web filter: agent-based | S11 | Filtering on laptops off-network | Web filtering that works even when laptops leave the office → Agent-based |
| Centralized proxy | S05 | Office proxy | All web traffic routed through one filtering server → Centralized proxy |
| Universal Resource Locator (URL) scanning | S05 | Proxy checks links | Checking URLs against known-bad lists before allowing access → URL scanning |
| Content categorization | S05 | Block "gambling", allow "news" | Filtering websites by category → Content categorization |
| Block rules | S05 | Block the typosquat domain | Explicitly denying specific sites → Block rules |
| Reputation | S05 | Block newly registered domains | Blocking sites based on a score of how trustworthy they are → Reputation |
| Operating system security: Group Policy | S03, S14 | GPO editor | Centrally managing Windows settings for users and computers → Group Policy |
| SELinux | S14 | `getenforce`, set enforcing | A Linux mandatory access control system → SELinux |
| Implementation of secure protocols: protocol selection | S14 | SFTP over FTP, SSH over Telnet, LDAPS over LDAP | The secure replacement for FTP using SSH → SFTP |
| Port selection | S14 | 636 not 389 | The port for LDAPS → 636 |
| Transport method | S14 | TLS vs IPSec | Choosing whether to secure traffic with TLS or IPSec is selecting a ______. → Transport method |
| DNS filtering | S36 | Block known malicious domains at the resolver | Blocking access to malicious domains at DNS resolution → DNS filtering |
| Email security: Domain-based Message Authentication Reporting and Conformance (DMARC) | S05 | Publish a DMARC record with p=quarantine | Tells receivers what to do with mail failing SPF/DKIM and where to report → DMARC |
| DomainKeys Identified Mail (DKIM) | S05 | Publish the DKIM public key | Signing outgoing mail so receivers can verify it wasn't altered → DKIM |
| Sender Policy Framework (SPF) | S05 | Fix the SPF TXT record | A DNS record listing servers allowed to send mail for a domain → SPF |
| Gateway | S05 | Email gateway quarantine | A device filtering inbound and outbound email for threats → Email gateway |
| File integrity monitoring | S17 | FIM alert on a changed system file | Detecting changes to important files → File integrity monitoring (FIM) |
| DLP | S24 | Write a DLP rule for account numbers | A DLP rule matching 16-digit card numbers in outbound email → Data loss prevention |
| Network access control (NAC) | S11 | Non-compliant laptop placed in a quarantine VLAN | Checking devices before allowing them onto the network → NAC |
| Endpoint detection and response (EDR)/extended detection and response (XDR) | S18 | Isolate host, view process tree | Endpoint tools that detect, investigate and respond to threats → EDR |
| User behavior analytics | S24 | UBA flags Dale | Detecting unusual activity by comparing it with normal patterns → User behavior analytics (UBA) |

## 4.6 Given a scenario, implement and maintain identity and access management

**Teaching approach.** The player's own onboarding (S01) teaches the user side. Directory Admin, IAM/SSO Console and PAM Vault cover the admin side. T03/T04 onboarding and offboarding tickets recur all game. S31 is the IAM failure story: Dale kept access he should not have.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Provisioning/de-provisioning user accounts | T03, T04, S31 | Create and remove accounts with the right groups | Removing access promptly when someone leaves → De-provisioning |
| Permission assignments and implications | T03, S31 | Permission creep found in Dale's account | Accumulating permissions over time from role changes → Permission creep |
| Identity proofing | S01, T02 | Verify the new hire's ID; verify a caller before reset | Verifying someone is who they claim before issuing credentials → Identity proofing |
| Federation | S08 | Trust between Paperkite's IdP and a partner | Linking identities across organizations so one login works for both → Federation |
| Single sign-on (SSO): Lightweight Directory Access Protocol (LDAP) | S07 | Ridgeway apps bind to the directory | The protocol for querying directory services, port 389 → LDAP |
| Open authorization (OAuth) | S08 | Grant an app access to a calendar | A framework for delegated authorization using tokens → OAuth |
| Security Assertions Markup Language (SAML) | S08 | Set up a SAML SSO app | An XML-based standard for exchanging authentication between IdP and service provider → SAML |
| Interoperability | S08 | Legacy app only speaks LDAP; bridge it | The ability of different identity systems to work together → Interoperability |
| Attestation | S31 | Quarterly access review: managers confirm each user's access | Managers formally confirming users' access is still correct → Attestation |
| Access controls: mandatory | S07 | Ridgeway's sealed court records with labels | Access decided by labels and clearances set by the system → MAC |
| Discretionary | T16 | File owner shares a folder | Access decided by the resource owner → DAC |
| Role-based | T03 | Groups by job role | Access assigned by job role → RBAC |
| Rule-based | S09 | Firewall-style rules | Access based on rules set by an administrator (e.g., firewall rules) → Rule-based access control |
| Attribute-based | S08 | Policy on department, device, location | Access decided by attributes of user, resource and environment → ABAC |
| Time-of-day restrictions | S24 | Tellers can't log in at 3 a.m. | Blocking logins outside working hours → Time-of-day restrictions |
| Least privilege | S01 | Minimum rights | Giving users only the access they need → Least privilege |
| Multifactor authentication implementations: biometrics | S01, S11 | Fingerprint on the phone | Using fingerprints or face recognition → Biometrics |
| Hard/soft authentication tokens | S01 | Key fob vs authenticator app | An authenticator app generating codes is a ______ token. → Soft |
| Security keys | S01 | FIDO2 key for admins | A USB/NFC device for phishing-resistant authentication → Security key |
| Factors: something you know | S01 | Password | A PIN is something you ______. → Know |
| Something you have | S01 | Phone, token | A smart card is something you ______. → Have |
| Something you are | S01 | Fingerprint | A retina scan is something you ______. → Are |
| Somewhere you are | S24 | Geolocation condition | Allowing login only from the office network uses ______. → Somewhere you are |
| Password concepts: length | S04 | Policy editor | The most important factor in password strength → Length |
| Complexity | S04 | Policy editor | Requiring mixed character types → Complexity |
| Reuse | S04 | Password history setting | Remembering previous passwords to stop users repeating them → Password history (reuse prevention) |
| Expiration | S04 | Max age | Forcing password changes after a period → Expiration |
| Age | S04 | Min age stops cycling back | A setting that stops users changing a password many times to reuse an old one → Minimum password age |
| Password managers | S04 | Set up the player's own | A tool that generates and stores unique passwords → Password manager |
| Passwordless | S08 | Passkeys at Paperkite | Authentication using keys or biometrics with no password → Passwordless |
| Privileged access management tools: just-in-time permissions | S31 | Elevation for one hour on approval | Granting elevated rights only when needed and for a limited time → Just-in-time permissions |
| Password vaulting | S31 | Check out the domain admin password | Storing privileged credentials in a secure vault with checkout → Password vaulting |
| Ephemeral credentials | S12 | Short-lived cloud tokens | Credentials that expire automatically after a short time → Ephemeral credentials |

## 4.7 Explain the importance of automation and orchestration related to secure operations

**Teaching approach.** Automation Studio lets the player build playbooks with drag-and-drop blocks. S12 automates Paperkite's provisioning and guard rails. T17 has the player automate a recurring ticket they've done by hand several times, so the time saved is felt. S35 shows the downside: an automation's service account is what Tidewater abuses.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Use case: user provisioning | T17 | Automate T03 onboarding | Automatically creating accounts from HR records → User provisioning |
| Resource provisioning | S12 | IaC templates | Automatically creating servers and storage → Resource provisioning |
| Guard rails | S12 | Block public buckets automatically | Automated limits that stop insecure configurations → Guard rails |
| Security groups | S12 | Auto-apply security group to new instances | Automatically applying network access rules to cloud resources → Security groups |
| Ticket creation | T17 | Alert creates ticket | Automatically opening tickets from alerts → Ticket creation |
| Escalation | T17 | Unacknowledged critical alert pages the on-call | Automatically raising unhandled issues to the next level → Escalation |
| Enabling/disabling services and access | S24 | Auto-disable account on DLP critical hit | Automatically turning off access when a threat is detected → Disabling access |
| Continuous integration and testing | S12 | Pipeline runs security tests on each commit | Automatically building and testing code on every change → Continuous integration |
| Integrations and application programming interfaces (APIs) | S12, T17 | Connect SIEM to ticketing via API | Letting tools exchange data and trigger actions automatically → APIs/integrations |
| Benefit: efficiency/time saving | T17 | Shift report shows minutes saved | Automation's most obvious benefit → Efficiency/time saving |
| Enforcing baselines | S14 | Auto-remediate drift | Automation keeps configurations matching the ______. → Baseline |
| Standard infrastructure configurations | S12 | Every server identical from template | Templates make every deployment use ______ configurations. → Standard |
| Scaling in a secure manner | S12 | Autoscaled instances inherit controls | New instances created by autoscaling still get security settings → Scaling securely |
| Employee retention | T17 | Analysts freed from boring tasks | Removing repetitive work helps ______. → Employee retention |
| Reaction time | S24 | Auto-disable in seconds vs minutes | Automation reduces ______ to threats. → Reaction time |
| Workforce multiplier | T17 | One analyst covers more clients | Automation lets a small team do the work of a larger one → Workforce multiplier |
| Consideration: complexity | S35 | Nobody understood the old script | A downside of automation: added ______. → Complexity |
| Cost | S12 | Tool licensing | Automation tools have upfront and ongoing ______. → Cost |
| Single point of failure | S35 | Automation server down = no provisioning | If all actions depend on one automation server, it is a ______. → Single point of failure |
| Technical debt | S35 | Quick scripts never maintained | Shortcuts in automation that cost more to fix later → Technical debt |
| Ongoing supportability | S35 | Who maintains the playbook after its author leaves? | Automation needs owners who can ______ it over time. → Support/maintain |

## 4.8 Explain appropriate incident response activities

**Teaching approach.** Act 3 (Glasshouse) walks the full process in order, with a phase tracker on screen. Act 4's insider case and Act 5's hunt add forensics and threat hunting. The Order card kind drills the sequence.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Process: preparation | S14, S23 | IR plan, tools, contacts ready before S16 | The IR phase covering plans, tools and training → Preparation |
| Detection | S17 | SIEM alert | The IR phase where an incident is first noticed → Detection |
| Analysis | S17, S19 | Confirm, scope, classify severity | Determining scope and impact of an incident → Analysis |
| Containment | S18 | Isolate hosts and segments | Limiting the spread of an incident → Containment |
| Eradication | S18, S22 | Remove malware, close the vendor access, reset credentials | Removing the cause of an incident → Eradication |
| Recovery | S22 | Restore and monitor | Restoring systems to normal operation → Recovery |
| Lessons learned | S23 | Post-incident meeting | Reviewing what happened to improve → Lessons learned |
| Training | S23 | Update training after Glasshouse | Teaching staff their IR roles before an incident → Training |
| Testing: tabletop exercise | S40, T20 | Conference room | A discussion-based IR test → Tabletop exercise |
| Testing: simulation | S40 | Full simulated attack | A hands-on exercise that acts out an incident → Simulation |
| Root cause analysis | S23 | Five-whys in Docs; trace to vendor remote access | Finding the underlying cause of an incident → Root cause analysis |
| Threat hunting | S35 | Proactive search with hypotheses in SIEM | Proactively searching for threats that evaded detection → Threat hunting |
| Digital forensics: legal hold | S31 | Preserve Dale's mailbox and files | A requirement to preserve data relevant to legal action → Legal hold |
| Chain of custody | S21, S31 | Evidence log in the locker; a gap ruins the evidence | A record of who handled evidence and when → Chain of custody |
| Acquisition | S21 | Image disk with write blocker; capture memory first | Collecting evidence in order of ______. → Volatility |
| Reporting | S21 | Forensic report in Docs | Documenting forensic findings for stakeholders or court → Reporting |
| Preservation | S21 | Hash images, store copies | Keeping evidence unchanged, proven by ______. → Hashes |
| E-discovery | S31 | Search mail for responsive documents | Finding and producing electronic information for legal cases → E-discovery |

## 4.9 Given a scenario, use data sources to support an investigation

**Teaching approach.** Investigations in S17, S19, S35 and T12 make the player pick and query the right data source. A "which source?" card kind shows a question ("Who logged in to the server at 2 a.m.?") and asks for the data source, before the player goes and queries it.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Log data: firewall logs | S17 | Allowed/denied connections | Which log shows connections blocked at the perimeter? → Firewall logs |
| Application logs | S29 | Web server logs show SQLi attempts | Which log shows a web app's requests and errors? → Application logs |
| Endpoint logs | S18 | EDR telemetry | Which logs show processes started on a laptop? → Endpoint logs |
| OS-specific security logs | S15, S35 | Windows Security log 4625/4624; `auth.log` | Which log records Windows login failures (event 4625)? → OS security log |
| IPS/IDS logs | S17 | Signature matches | Which logs show signature matches on network traffic? → IDS/IPS logs |
| Network logs | S19 | Switch, router, DHCP, DNS logs | Which logs map an IP to a MAC at a given time? → DHCP/network logs |
| Metadata | S24 | Email headers, file properties show the real author | Data about data, like email headers or file timestamps → Metadata |
| Data sources: vulnerability scans | S16 | The exploited flaw was already on last month's scan | Which source shows whether the exploited weakness was known? → Vulnerability scans |
| Automated reports | S17 | Nightly SIEM report shows the first sign | Scheduled summaries generated by tools → Automated reports |
| Dashboards | S17 | SIEM dashboard | Real-time visual summaries of security data → Dashboards |
| Packet captures | S19 | Packet Viewer | Which source shows the full content of network traffic? → Packet captures |

**Checked task (S19).** From a 10,000-flow NetFlow export and a packet capture, find the infected host, the C2 domain, the beacon interval, and the exfil volume. The checker validates each answer against the simulation's ground truth.
