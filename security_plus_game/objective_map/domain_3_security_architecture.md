# Domain 3: Security Architecture (18%)

[Back to the map](README.md)

## 3.1 Compare and contrast security implications of different architecture models

**Teaching approach.** The five clients are five architectures: Paperkite is cloud-native (serverless, containers, microservices, IaC), Brightwater is ICS/SCADA with RTOS controllers, Harbor is on-premises with embedded medical IoT, Ridgeway is centralized legacy, Copperline is hybrid. The player builds or changes each in Act 2 and then sees how each architecture behaves under attack. A recurring **trade-off card** kind asks "which consideration does this choice hurt?" using the list of considerations below.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Cloud: responsibility matrix | S12, S26 | Cloud Console shows a shared responsibility panel per service (IaaS, PaaS, SaaS); player assigns who patches what | In IaaS, who is responsible for patching the guest OS? → The customer |
| Cloud: hybrid considerations | S08, S33 | Copperline syncs on-prem directory to cloud IdP | Running both on-premises and cloud systems together → Hybrid cloud |
| Cloud: third-party vendors | S27 | Paperkite's SaaS dependencies | Each cloud vendor you add extends your ______ risk. → Third-party/supply chain |
| Infrastructure as code (IaC) | S12 | Edit a template; a guard-rail check blocks a public bucket | Defining infrastructure in machine-readable files → IaC |
| Serverless | S12 | Paperkite's thumbnail function; the provider runs the servers | Running code without managing servers, billed per execution → Serverless |
| Microservices | S12 | Paperkite's app split into services with their own permissions | An app built as small, independent services communicating via APIs → Microservices |
| Network infrastructure: physical isolation (air-gapped) | S09, S38 | Brightwater's safety system is air-gapped; a contractor's USB crosses it | A network with no physical connection to others → Air-gapped |
| Logical segmentation | S09 | VLANs | Separating networks with VLANs or rules on shared hardware → Logical segmentation |
| Software-defined networking (SDN) | S12 | Cloud VPC rules; control vs data plane | Separating the network's control plane from the data plane in software → SDN |
| On-premises | S13 | Harbor's own server room | Infrastructure the organization owns and runs in its own facility → On-premises |
| Centralized vs decentralized | S07, S32 | Ridgeway central IT vs departments running their own systems | A single point of control and policy enforcement → Centralized |
| Containerization | S12 | Containers share the host kernel; image scanning | Packaging apps with dependencies, sharing the host OS kernel → Containerization |
| Virtualization | S12, S14 | Lantern's lab hypervisor | Running multiple OS instances on one physical host via a hypervisor → Virtualization |
| IoT | S13 | Smart thermostats and badge readers | Network-connected everyday devices with weak default security → IoT |
| Industrial control systems (ICS) / SCADA | S09, S38 | SCADA HMI app; PLCs | A system that monitors and controls industrial processes over wide areas → SCADA |
| Real-time operating system (RTOS) | S09, S38 | PLC controllers must respond in milliseconds; can't run agents | An OS that must respond within strict time limits → RTOS |
| Embedded systems | S13 | Infusion pumps | A computer built into a device for one dedicated function → Embedded system |
| High availability | S22, S36 | Clustered EHR, load-balanced web | Systems designed to stay up with minimal downtime → High availability |
| Consideration: availability | S38 | Patch now vs keep the plant running | A plant that cannot be taken down to patch prioritizes ______. → Availability |
| Resilience | S22 | Recovers from failure | The ability to keep working or recover quickly after failure → Resilience |
| Cost | S12 | Budget panel on each architecture choice | Choosing on-prem HSMs over cloud KMS mainly affects ______. → Cost |
| Responsiveness | S12 | Latency of serverless cold starts | How quickly a system reacts to requests → Responsiveness |
| Scalability | S12 | Autoscaling | The ability to handle growth in load → Scalability |
| Ease of deployment | S12 | IaC vs manual builds | IaC mainly improves ease of ______. → Deployment |
| Risk transference | S12, S30 | Moving to SaaS shifts some risk to the provider | Moving to a cloud provider can ______ some risks. → Transfer |
| Ease of recovery | S22 | Rebuild from IaC vs from scratch | Infrastructure defined as code improves ease of ______. → Recovery |
| Patch availability | S13 | Vendor stopped shipping patches | End-of-life systems lack patch ______. → Availability |
| Inability to patch | S13, S38 | PLCs and imaging PCs; use compensating controls | When a system cannot be patched, use ______ controls. → Compensating |
| Power | S38 | Edge devices with limited power | IoT sensors running on batteries are constrained by ______. → Power |
| Compute | S38 | PLCs too weak to run encryption or agents | Embedded devices often cannot run strong encryption because of limited ______. → Compute |

## 3.2 Given a scenario, apply security principles to secure enterprise infrastructure

**Teaching approach.** The **network diagram Place view** is the main mechanic. The player places appliances, chooses inline or tap, active or passive, sets failure modes, and draws zones. Because the diagram is the live simulation, a scenario's attacker script then runs and the player sees what each placement caught or missed.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Device placement | S09 | Place IDS, firewall, jump server on the Brightwater diagram | Where should a network IDS sensor go to see traffic between IT and OT? → On the boundary between zones (span/tap) |
| Security zones | S09 | Draw internal, screened subnet, OT and management zones | Areas of a network grouped by trust level → Security zones |
| Attack surface | S09, S14 | Attack surface overlay shrinks as the player works | All the points where an attacker could try to get in → Attack surface |
| Connectivity | S09, S11 | Decide which links exist at all | Removing unneeded connections between zones reduces ______. → Attack surface |
| Failure modes: fail-open | S10, S38 | Door lock on fire exit must fail open (life safety) | A device that allows traffic or access when it fails → Fail-open |
| Failure modes: fail-closed | S09, S38 | Firewall between IT and OT fails closed | A device that blocks traffic or access when it fails → Fail-closed |
| Device attribute: active vs passive | S09 | IPS (active) vs IDS (passive) | A device that can block traffic is ______; one that only watches is ______. → Active; passive |
| Device attribute: inline vs tap/monitor | S09 | Drag the sensor onto the wire vs onto a span port | An IPS must be placed ______ to block. → Inline |
| Network appliances: jump server | S09 | All OT admin goes through `jump-01` | A hardened host used as the only way to administer a secure zone → Jump server |
| Network appliances: proxy server | S05, S17 | Web proxy logs and blocks | A server that makes requests on behalf of clients, often filtering them → Proxy server |
| Network appliances: IPS/IDS | S09, S17 | Place and tune | Detects and blocks attacks inline → IPS |
| Network appliances: load balancer | S36 | Spread web traffic across servers | Distributing traffic across multiple servers → Load balancer |
| Network appliances: sensors | S09 | Place OT sensors | Devices that collect network data for security tools → Sensors |
| Port security | S10 | Switch CLI: limit MACs on the pump station lobby port | Limiting which devices can use a switch port, e.g., by MAC → Port security |
| 802.1X | S11 | Configure switch and AP to require 802.1X | Port-based network access control requiring authentication before access → 802.1X |
| Extensible Authentication Protocol (EAP) | S11 | Choose EAP-TLS with device certs | The authentication framework used with 802.1X → EAP |
| Firewall types: web application firewall (WAF) | S36, S29 | Put a WAF in front of the payment site | A firewall that inspects HTTP to block attacks like SQLi and XSS → WAF |
| Unified threat management (UTM) | S07 | Ridgeway's all-in-one box | One appliance combining firewall, IPS, antivirus, filtering → UTM |
| Next-generation firewall (NGFW) | S09 | Application-aware rules | A firewall that inspects applications and users, not just ports → NGFW |
| Layer 4/Layer 7 | S09, S36 | Compare a port rule with an app rule | A firewall filtering on IP and port works at layer ______. → 4 |
| Virtual private network (VPN) | S16, S08 | Vendor VPN vs zero trust access | An encrypted tunnel over an untrusted network → VPN |
| Remote access | S16 | Vendor remote support tool, made MFA-only and time-limited | Securing vendor remote access: MFA, time limits and ______. → Session monitoring/least privilege |
| Tunneling: Transport Layer Security (TLS) | S08 | TLS-based VPN to the access proxy | A VPN that runs over HTTPS uses ______. → TLS |
| Tunneling: Internet Protocol Security (IPSec) | S16 | Site-to-site tunnel; AH vs ESP cards | The IPSec protocol that provides encryption → ESP |
| Software-defined wide area network (SD-WAN) | S11 | Copperline branches over internet links | Using software to manage WAN connections across branches → SD-WAN |
| Secure access service edge (SASE) | S08 | Paperkite's cloud security edge | Combining network and security services (SWG, CASB, ZTNA) delivered from the cloud → SASE |
| Selection of effective controls | S09, S40 | Budget-limited choice among controls for a stated risk | Choosing controls based on risk, cost and fit → Selection of effective controls |

**Checked task (S09).** On the Brightwater diagram: OT zone behind a fail-closed NGFW, only `jump-01` can reach OT on Modbus/TCP (502), IDS on a tap at the boundary, no direct internet route to OT. Then Jules runs the attacker script and the player sees each step blocked or logged.

## 3.3 Compare and contrast concepts and strategies to protect data

**Teaching approach.** S06 has each client describe what they store; the player classifies it. T16 has the player label a file share in Files, and DLP (4.5) acts on the labels. S26 is where sovereignty and geographic restrictions matter, because Paperkite's EU customers' data must stay in an EU region.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Data type: regulated | S06 | Patient records (HIPAA), card data (PCI DSS) | Data whose handling is governed by law or regulation → Regulated data |
| Trade secret | S06 | Paperkite's ranking algorithm | Confidential business information that gives a competitive edge → Trade secret |
| Intellectual property | S06 | Paperkite source code | Creations of the mind protected by law, like code and designs → Intellectual property |
| Legal information | S31 | Case files on Dale | Contracts, case files and legal advice are ______ information. → Legal |
| Financial information | S06 | Copperline account data | Bank account and transaction records → Financial information |
| Human-readable | T16 | Spreadsheets | Data a person can read directly → Human-readable |
| Non-human-readable | T16 | Barcodes, encrypted blobs, binary | Data that needs a machine to interpret, like a QR code → Non-human-readable |
| Classification: sensitive | T16 | Labels in Files | Information whose disclosure could cause harm, such as PII → Sensitive |
| Confidential | T16 | Internal pricing | Information for authorized people only, with harm if leaked → Confidential |
| Public | T16 | Press releases | Information that can be freely shared → Public |
| Restricted | T16 | Executive merger plans | The most limited access; serious harm if disclosed → Restricted |
| Private | T16 | Employee personal info | Personal information about individuals → Private |
| Critical | T16 | Plant setpoints | Data essential to keep the organization running → Critical |
| Data state: at rest | S04 | Encrypted disk | Data stored on a drive or in a database → Data at rest |
| Data state: in transit | S19 | Packet Viewer | Data moving across a network → Data in transit |
| Data state: in use | S33 | Data decrypted in memory; secure enclave | Data being processed in memory → Data in use |
| Data sovereignty | S26 | EU customer data in EU region | Data being subject to the laws of the country where it is stored → Data sovereignty |
| Geolocation | S26 | Region picker; geolocation-based access | Using location to decide where data is stored or who may access it → Geolocation |
| Methods: geographic restrictions | S26 | Block admin access from outside approved countries | Limiting access by user location → Geographic restrictions |
| Encryption | S04, S33 | See 1.4 | Protecting confidentiality by making data unreadable without a key → Encryption |
| Hashing | S21 | Evidence integrity | Verifying data has not changed → Hashing |
| Masking | S33 | Call center sees last 4 digits | Hiding parts of data from users who don't need it → Masking |
| Tokenization | S33 | Card numbers replaced | Replacing data with a token mapped in a secure vault → Tokenization |
| Obfuscation | S12 | Obfuscated client-side code | Making data or code hard to understand without changing what it does → Obfuscation |
| Segmentation | S33 | Card data environment on its own network | Isolating sensitive data on separate networks or systems → Segmentation |
| Permission restrictions | T16 | Folder ACLs follow the classification | Limiting who can read or change data based on need → Permission restrictions |

## 3.4 Explain the importance of resilience and recovery in security architecture

**Teaching approach.** S22 (Harbor restore) and S38 (Brightwater under attack) are the big ones. The Backup Manager app lets the player configure and, crucially, **test** backups. A **restore test** chore recurs whenever backup cards are due, and an untested backup set in S22 turns out to be corrupt, which is the lesson.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| High availability: load balancing vs clustering | S22, S36 | Web tier load balanced; EHR database clustered | Multiple servers acting as one system, with failover between them → Clustering |
| Site considerations: hot | S22 | Decide where imaging moves | A fully equipped site ready to take over almost immediately → Hot site |
| Cold | S22 | Cheapest option, weeks to restore | A site with space and power but no equipment ready → Cold site |
| Warm | S22 | Middle option chosen for Harbor imaging | A site with some equipment, needing data and setup to go live → Warm site |
| Geographic dispersion | S22 | Backup site in a different flood zone | Placing sites far enough apart that one disaster cannot hit both → Geographic dispersion |
| Platform diversity | S38 | Two vendors of PLC so one exploit can't hit both | Using different OSs or vendors so one flaw can't take down everything → Platform diversity |
| Multi-cloud systems | S12 | Paperkite's DR copy in a second provider | Using more than one cloud provider for resilience → Multi-cloud |
| Continuity of operations | S38 | Run the plant manually per the COOP plan | Plans to keep essential functions running during a disruption → Continuity of operations (COOP) |
| Capacity planning: people | S38 | Enough trained operators for manual mode | Making sure enough skilled staff are available in a crisis → Capacity planning (people) |
| Capacity planning: technology | S36 | Can the site handle 10× traffic? | Ensuring systems can handle expected and peak load → Capacity planning (technology) |
| Capacity planning: infrastructure | S38 | Power, cooling, network headroom | Ensuring facilities and networks can support growth → Capacity planning (infrastructure) |
| Testing: tabletop exercises | S40, T20 | Conference room discussion with decision cards | A discussion-based walk-through of a scenario with no systems touched → Tabletop exercise |
| Testing: fail over | S22 | Actually fail over the EHR cluster | Switching to a backup system to confirm it works → Failover test |
| Testing: simulation | S40 | A full simulated attack day | A realistic exercise acting out an incident → Simulation |
| Testing: parallel processing | S22 | Run the warm site in parallel before cutover | Running the backup site alongside the primary to compare results → Parallel processing test |
| Backups: onsite/offsite | S22 | Onsite copy was encrypted by ransomware; offsite survived | Why keep an offsite backup? → So one event (fire, ransomware) cannot destroy all copies |
| Backups: frequency | S22 | Nightly vs hourly; ties to RPO | How often backups run determines the ______. → Recovery point (RPO) |
| Backups: encryption | S22 | Encrypt backup media | Backups should be encrypted because they hold the same ______ as production. → Sensitive data |
| Backups: snapshots | S12, S22 | VM snapshot before a change | A point-in-time copy of a system's state → Snapshot |
| Backups: recovery | S22 | Restore and verify | A backup you haven't tested restoring is ______. → Unproven |
| Backups: replication | S22 | Real-time copy to the warm site | Continuously copying data to another location → Replication |
| Backups: journaling | S22 | Database journal lets you replay to just before the attack | Logging changes so data can be rebuilt to a point in time → Journaling |
| Power: generators | S38 | Start the plant generator; fuel decision | Long-term backup power for an outage → Generator |
| Power: uninterruptible power supply (UPS) | S38 | UPS covers the gap until the generator starts | Short-term battery power that keeps systems on during a switch → UPS |
