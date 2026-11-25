# Domain 2: Threats, Vulnerabilities, and Mitigations (22%)

[Back to the map](README.md)

## 2.1 Compare and contrast common threat actors and motivations

**Teaching approach.** Each actor type is a real recurring antagonist (see [cast](../02_world_cast_and_campaign.md#threat-actors-one-per-actor-type-in-objective-21)). The SOC has an **actor board** on the wall. After each incident, the player pins the evidence to an actor card and tags attributes and motivation, a Match beat that is checked against what the scenario revealed. Wrong pins are corrected by Priya with the clue they missed.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Nation-state | S06, S34–S40 | Tidewater: patient, well funded, targets infrastructure | A well-funded government-backed group with advanced, persistent capability → Nation-state |
| Unskilled attacker | S15 | zer0cool_17 uses a bought kit, noisy | An attacker using tools others wrote, with little skill → Unskilled attacker |
| Hacktivist | S36 | Open Valve defaces the utility site with a political message | An attacker driven by a political or social cause → Hacktivist |
| Insider threat | S24, S31 | Dale at Copperline | A threat from someone with authorized access → Insider threat |
| Organized crime | S16–S23 | Glasshouse ransomware | A professional group motivated mainly by money → Organized crime |
| Shadow IT | S14, T14 | Paperkite marketing's unsanctioned SaaS | IT systems used without the IT department's approval → Shadow IT |
| Attribute: internal/external | Actor board | Tag each actor | Is an insider an internal or external actor? → Internal |
| Attribute: resources/funding | Actor board | Compare Tidewater to zer0cool | Which actor type usually has the most resources? → Nation-state |
| Attribute: level of sophistication/capability | Actor board | Same | Which actor has the lowest sophistication? → Unskilled attacker |
| Motivation: data exfiltration | S19 | Glasshouse steals patient data before encrypting | Stealing data out of an organization → Data exfiltration |
| Espionage | S35 | Tidewater maps the plant | Secretly gathering information for a state or competitor → Espionage |
| Service disruption | S36 | Open Valve DDoS | A DDoS against the utility's payment site aims at ______. → Service disruption |
| Blackmail | S20 | Leak threat | Threatening to release data unless paid → Blackmail |
| Financial gain | S20 | Ransom demand | The most common motivation of organized crime → Financial gain |
| Philosophical/political beliefs | S36 | Open Valve manifesto | Hacktivists are driven by ______ beliefs. → Philosophical/political |
| Ethical | S29 | A researcher reports a bug to Ridgeway | A hacker who finds and reports flaws to help → Ethical motivation |
| Revenge | S24 | Dale's backstory | An employee passed over for promotion who sabotages systems → Revenge |
| Disruption/chaos | S15 | zer0cool just wants to cause trouble | Attacks for fun or chaos, with no clear gain → Disruption/chaos |
| War | S38, S40 | Tidewater's pre-positioning to disable water in a conflict | Nation-states attacking infrastructure as part of armed conflict → War |

## 2.2 Explain common threat vectors and attack surfaces

**Teaching approach.** Each vector arrives through the game's own channels: Mail, Chat, a phone call scene, the parking lot, the vendor's remote tool. The player inspects it, names the vector on a card, and closes the hole. An **attack surface** overlay on the network diagram (S09, S14) shows open ports, default creds, and unsupported systems as glowing points the player reduces over Act 2.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Message-based: email | S05, T01 | Phish in Mail; inspect headers | The most common threat vector for phishing → Email |
| SMS | S05 | Fake "bank alert" text to a Copperline teller | Phishing by text message → Smishing |
| Instant messaging (IM) | S05 | Chat message from a "colleague" with a link | Malicious links sent over chat apps use the ______ vector. → Instant messaging |
| Image-based | S24 | Image carrying hidden data or a malicious payload | An attack hidden inside an image file is ______-based. → Image |
| File-based | S03, S16 | Macro document, trojan executable | A malicious macro in a document is a ______-based vector. → File |
| Voice call | S05, T02 | "IT help desk" call scene asking for MFA code | Phishing over a phone call → Vishing |
| Removable device | S03 | USB drop | Infected USB drives left for staff to find → Removable device (baiting) |
| Vulnerable software: client-based vs agentless | S28 | Vuln scanner modes; a vulnerable agent on hosts | Software that must be installed on each device to work is ______-based. → Client |
| Unsupported systems and applications | S13 | Windows 7 imaging PCs | Systems no longer receiving vendor patches → Unsupported (end-of-life) |
| Unsecure networks: wireless | S11 | Open guest Wi-Fi bridged to staff | An open Wi-Fi network that reaches internal systems is an ______ network. → Unsecure |
| Unsecure networks: wired | S10 | Live network jack in the pump station lobby | A live wall jack in a public area is an unsecure ______ network. → Wired |
| Unsecure networks: Bluetooth | S11 | Discoverable devices; bluejacking/bluesnarfing cards | Stealing data over Bluetooth → Bluesnarfing |
| Open service ports | S09, S14 | `ss -tulpn`, scanner; close Telnet | Every listening port increases the ______. → Attack surface |
| Default credentials | S09, S14 | HMI still on admin/admin | Vendor-set usernames and passwords that were never changed → Default credentials |
| Supply chain: managed service providers (MSPs) | S16, S27 | The imaging vendor's access; Lantern itself is an MSP | An attacker who compromises an MSP can reach all of its ______. → Customers |
| Supply chain: vendors | S16, S34 | Remote support tool, SCADA vendor update | An attack via a trusted vendor's product is a ______ attack. → Supply chain |
| Supply chain: suppliers | S13 | Counterfeit network card in a shipment | Tampered hardware from a parts supplier is a supply chain risk at the ______ level. → Supplier/hardware |
| Phishing | S05, T01 | Report Phish button, header analysis | Fraudulent email to trick users into revealing info or clicking → Phishing |
| Vishing | S05, T02 | Phone call scene | Voice phishing → Vishing |
| Smishing | S05 | SMS scene | SMS phishing → Smishing |
| Misinformation/disinformation | S36 | Open Valve spreads false "water unsafe" claims | False information spread on purpose → Disinformation |
| Impersonation | T02, S05 | Caller claims to be Marcus | Pretending to be someone else to gain trust → Impersonation |
| Business email compromise | S05, S24 | Fake CFO wire request at Copperline | Using a real or spoofed executive email account to request payments → BEC |
| Pretexting | T02, S37 | "I'm here to fix the HVAC" | Inventing a scenario to get information → Pretexting |
| Watering hole | S34 | A water-industry forum site is compromised | Infecting a site the target group is known to visit → Watering hole |
| Brand impersonation | S05 | Fake "PayFlow" login page | A fake site copying a known company's look → Brand impersonation |
| Typosquatting | S05 | `copperIine.example` with a capital I | Registering misspelled domain names to catch typos → Typosquatting |

## 2.3 Explain various types of vulnerabilities

**Teaching approach.** Vulnerabilities appear as scanner findings (S28), code review findings (S12, T19), pentest findings with Jules (S29), and real exploited holes in incidents. In the pentest range the player triggers SQL injection and XSS against a deliberately vulnerable fictional app to see the effect, then fixes it in the Code Review app with input validation.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Memory injection | S35 | Tidewater injects into a legitimate process; EDR shows it | Inserting malicious code into a running process's memory → Memory injection |
| Buffer overflow | S29 | Jules demonstrates a crash in a legacy kiosk app | Writing more data to a buffer than it holds, overwriting memory → Buffer overflow |
| Race conditions | T19 | Code review: check-then-use on a file | A flaw where timing between operations can be exploited → Race condition |
| Time-of-check (TOC) / time-of-use (TOU) | T19 | Same, named | A race condition between checking a resource and using it → TOCTOU |
| Malicious update | S34 | Poisoned SCADA vendor update | A legitimate-looking software update that carries malware → Malicious update |
| Operating system (OS)-based | S28 | Unpatched kernel finding | A vulnerability in the OS itself, fixed by OS patches → OS-based |
| Web-based: SQL injection | S29 | Range: login bypass with a stand-in payload; fix with parameterized queries | Inserting SQL into an input to change the database query → SQL injection (SQLi) |
| Web-based: cross-site scripting | S29 | Range: script stored in a comment field; fix with output encoding | Injecting scripts into a site that run in other users' browsers → XSS |
| Hardware: firmware | S13, S28 | Outdated BIOS/firmware on infusion pumps | Vulnerabilities in the low-level software that runs hardware → Firmware |
| Hardware: end-of-life | S13 | EOL network switch | Hardware the vendor no longer supports or patches → End-of-life |
| Hardware: legacy | S07, S13 | Old records server | Older systems still in use that may lack modern security → Legacy |
| Virtualization: VM escape | S12 | Briefing on hypervisor patch urgency | Breaking out of a VM to reach the host or other VMs → VM escape |
| Virtualization: resource reuse | S12 | Memory not cleared between tenants | Data left in reallocated memory or storage that another VM can read → Resource reuse |
| Cloud-specific | S12, S26 | Public storage bucket, over-permissive role | A misconfigured public storage bucket is a ______ vulnerability. → Cloud-specific |
| Supply chain: service provider | S16 | Vendor remote access | A breach at a provider you depend on → Service provider supply chain risk |
| Supply chain: hardware provider | S13 | Counterfeit parts | Compromised or counterfeit components → Hardware provider risk |
| Supply chain: software provider | S34, S12 | Malicious package in a dependency | Malicious code in a third-party library → Software provider risk |
| Cryptographic | S33 | Weak ciphers, short keys, expired certs | Using outdated algorithms like MD5 or DES is a ______ vulnerability. → Cryptographic |
| Misconfiguration | S14, S12 | Most findings in the game | Insecure settings, such as defaults or open permissions → Misconfiguration |
| Mobile device: side loading | S11 | MDM finds an app installed from outside the store | Installing apps from outside the official app store → Side loading |
| Mobile device: jailbreaking | S11 | MDM flags a jailbroken phone | Removing a phone's built-in restrictions to gain full control → Jailbreaking (rooting on Android) |
| Zero-day | S34 | Tidewater uses an unknown flaw | A vulnerability unknown to the vendor with no patch yet → Zero-day |

## 2.4 Given a scenario, analyze indicators of malicious activity

**Teaching approach.** This is a "given a scenario" objective, so it is mostly **Computer** beats in the SIEM, Packet Viewer, Flow Viewer and logs, and the player must identify the attack from evidence before naming it on a card. Free Shift tickets draw heavily from this objective.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Ransomware | S17–S22 | Encrypted files, ransom note, mass file renames in FIM | Malware that encrypts data and demands payment → Ransomware |
| Trojan | S03 | USB "salaries" executable | Malware disguised as legitimate software → Trojan |
| Worm | S18 | Spreads across Harbor's flat VLAN via SMB | Malware that self-replicates across networks without user action → Worm |
| Spyware | S24 | Found on Dale's victim's PC | Malware that secretly monitors user activity → Spyware |
| Bloatware | S11 | Pre-installed apps on COPE phones | Unwanted pre-installed software that uses resources and adds attack surface → Bloatware |
| Virus | S03 | Infected macro | Malware that attaches to files and needs a user to run it → Virus |
| Keylogger | S24 | Dale captures a manager's password | Malware or hardware recording keystrokes → Keylogger |
| Logic bomb | S31 | Dale's scheduled task set to wipe a share if his account is disabled | Malicious code that runs when a condition is met → Logic bomb |
| Rootkit | S35 | Hidden process visible only from memory capture | Malware that hides itself at a deep level, often with admin/kernel access → Rootkit |
| Physical: brute force | S37 | Forced door at pump station | Forcing a door or lock open is a physical ______ attack. → Brute force |
| Physical: RFID cloning | S37 | Badge logs show a badge used in two places | Copying an access badge's signal to make a duplicate → RFID cloning |
| Physical: environmental | S37 | HVAC tampered so the control room overheats | Attacking power, cooling or fire systems to cause failure → Environmental attack |
| Network: DDoS amplified | S36 | Flow Viewer: small requests, huge responses | A DDoS that uses small requests to trigger large responses → Amplification |
| Network: DDoS reflected | S36 | Spoofed source IPs; responses hit the victim | A DDoS that spoofs the victim's address so third parties flood it → Reflection |
| Network: DNS attacks | S36 | Poisoned resolver sends users to a fake site | Corrupting DNS so a name resolves to an attacker's address → DNS poisoning |
| Network: wireless | S11 | Evil twin AP in the Copperline branch; deauth floods | A fake access point with a legitimate network's name → Evil twin |
| Network: on-path | S19 | ARP table shows duplicate MACs; Packet Viewer shows relayed traffic | An attacker secretly relaying and possibly altering traffic between two parties → On-path attack |
| Network: credential replay | S19 | Captured NTLM hash reused | Reusing captured credentials or hashes to authenticate → Credential replay |
| Network: malicious code | S16 | Script delivered over the network | Malware delivered over the network, such as scripts or macros → Malicious code |
| Application: injection | S29 | SQLi in logs | A web log entry containing `' OR 1=1 --` indicates ______. → SQL injection |
| Application: buffer overflow | S29 | Crash logs with long input | Long repeated input followed by a crash suggests ______. → Buffer overflow |
| Application: replay | S19 | Same session token used twice from different IPs | Capturing and resending valid data to repeat an action → Replay attack |
| Application: privilege escalation | S29, S35 | `whoami /priv` change; event 4672 | Gaining higher rights than intended → Privilege escalation |
| Application: forgery | S29 | CSRF on Ridgeway's form | Tricking a user's browser into sending an unwanted authenticated request → Cross-site request forgery (CSRF) |
| Application: directory traversal | S29 | `../../etc/passwd` in web logs | Using `../` in paths to read files outside the web root → Directory traversal |
| Cryptographic: downgrade | S33 | Packet Viewer: client forced to an old TLS version | Forcing a connection to use a weaker protocol or cipher → Downgrade attack |
| Cryptographic: collision | S33 | Two files, same MD5 | Two different inputs producing the same hash → Collision |
| Cryptographic: birthday | S33 | Explained via collisions | An attack using probability to find hash collisions faster than brute force → Birthday attack |
| Password: spraying | S15 | Many accounts, one password each, in auth logs | Trying a few common passwords against many accounts → Password spraying |
| Password: brute force | S15 | Many attempts on one account | Trying every possible password → Brute force |
| Indicator: account lockout | S15 | Lockout events (4740) spike | Many lockouts at once can indicate ______. → Brute force or spraying |
| Indicator: concurrent session usage | T12 | Same user active from two places | One account logged in from two locations at once is an indicator of ______. → Compromised credentials |
| Indicator: blocked content | S17 | Proxy blocks to known C2 domains | Repeated proxy blocks to a malicious domain suggest an infected ______. → Host |
| Indicator: impossible travel | S24, T12 | Logins from two countries 20 minutes apart | Logins from locations too far apart for the time between them → Impossible travel |
| Indicator: resource consumption | S35 | CPU spikes on an HMI | Unexpected high CPU, memory or bandwidth use → Resource consumption indicator |
| Indicator: resource inaccessibility | S17 | Files cannot be opened | Users suddenly unable to open files may indicate ______. → Ransomware |
| Indicator: out-of-cycle logging | S35 | Logs generated at odd times | Log entries at unusual times or frequencies → Out-of-cycle logging |
| Indicator: published/documented | S39 | A CISA-style advisory lists IoCs; search for them | Indicators from threat reports or advisories → Published/documented IoCs |
| Indicator: missing logs | S35 | Event 1102 (log cleared), gap in timeline | Gaps in logs may mean an attacker ______ them. → Cleared or tampered with |

## 2.5 Explain the purpose of mitigation techniques used to secure the enterprise

**Teaching approach.** Every mitigation is something the player deploys in Act 2 that then stops (or fails to stop) an attack in Acts 3 and 5, via the controls register. S14 is the hardening checklist scenario.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Segmentation | S09, S18 | VLANs and firewall zones; Glasshouse stops at the boundary if done | Dividing a network into zones to limit spread → Segmentation |
| Access control: access control list | S09, T05 | Write ACLs on the router | A list of rules permitting or denying traffic or access → ACL |
| Access control: permissions | S14, T16 | NTFS/Linux permissions on shares | Read, write and execute rights on a file are ______. → Permissions |
| Application allow list | S13, S14 | Imaging PCs only run approved apps | Only explicitly approved software can run → Application allow list |
| Isolation | S18 | Isolate a host in EDR | Separating an infected or risky system from the network → Isolation |
| Patching | S28 | Patch cycle with the scanner | Applying vendor updates to fix vulnerabilities → Patching |
| Encryption | S04, S33 | Encrypt laptops and data at rest | Mitigating data theft from lost laptops → Full-disk encryption |
| Monitoring | S17 | SIEM coverage | Continuous watching of systems to detect issues → Monitoring |
| Least privilege | S01, S31 | Remove local admin rights | Giving users only the access they need → Least privilege |
| Configuration enforcement | S14 | Baseline drift auto-corrected by GPO/MDM | Automatically keeping systems matching approved settings → Configuration enforcement |
| Decommissioning | S07, T07 | Remove the old server properly | Retiring systems securely, including data removal → Decommissioning |
| Hardening: encryption | S14 | Checklist item | Turning on disk encryption is a ______ technique. → Hardening |
| Hardening: installation of endpoint protection | S14 | Deploy EDR agent | Installing antivirus/EDR on every endpoint → Endpoint protection |
| Hardening: host-based firewall | S14 | Configure on each server | A firewall running on the individual host → Host-based firewall |
| Hardening: host-based intrusion prevention system (HIPS) | S14 | Enable on kiosks | Software on a host that detects and blocks attacks → HIPS |
| Hardening: disabling ports/protocols | S14, S09 | Disable Telnet, SMBv1, unused switch ports | Turning off Telnet and unused switch ports is ______. → Disabling ports/protocols |
| Hardening: default password changes | S14, S09 | Change HMI and router defaults | The first hardening step for a new network device → Change the default password |
| Hardening: removal of unnecessary software | S14, S11 | Remove bloatware and unused services | Uninstalling unused software reduces the ______. → Attack surface |
