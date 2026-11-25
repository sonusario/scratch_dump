# Domain 1: General Security Concepts (12%)

[Back to the map](README.md)

## 1.1 Compare and contrast various types of security controls

**Teaching approach.** S02 is a walk around Lantern with Priya. Every object she points at (the badge reader, the "Authorized Personnel Only" sign, the backup job, the policy binder) is a card that asks for its category and its type. Later, every control the player deploys goes into the **controls register**, and the player must tag it with a category and type when they add it, so the classification habit is practiced for the whole game. The Match card kind (control → type) is heavily used here.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Category: technical | S02, register | Inspect the firewall appliance and the login screen, tag them | A firewall rule is which control category? → Technical |
| Category: managerial | S02, S30, S32 | Inspect the risk assessment binder; write a policy in S32 | Risk assessments and security policies are ______ controls. → Managerial |
| Category: operational | S02, S05 | Inspect the guard's patrol schedule, the awareness training roster | Controls carried out by people day to day (training, guard patrols) are which category? → Operational |
| Category: physical | S02, S10 | Inspect the fence, lock, bollards; place them in S10 | Bollards are which control category? → Physical |
| Type: preventive | S02, S09 | Firewall deny rule, door lock | A control that stops an incident before it happens is ______. → Preventive |
| Type: deterrent | S02, S10 | Warning sign, visible camera, lighting | A sign reading "Premises under video surveillance" is mainly which type? → Deterrent |
| Type: detective | S02, S17 | IDS, log review, motion sensor | IDS alerts and log reviews are ______ controls. → Detective |
| Type: corrective | S18, S22 | Restore from backup, EDR quarantine, reimaging | Restoring from backup after an incident is which control type? → Corrective |
| Type: compensating | S13, S07 | Unpatchable imaging PCs get isolation instead of patches | A control used when the primary control cannot be implemented is ______. → Compensating |
| Type: directive | S01, S32 | AUP, "badges must be visible" policy | A policy that tells people what to do is which control type? → Directive |

**Checked task (S02 end).** In the Docs app, fill a gap-analysis table for Lantern's lobby with each control's category and type; the checker validates each tag.

## 1.2 Summarize fundamental security concepts

**Teaching approach.** CIA and AAA are introduced through the player's own onboarding (S01). Zero trust is a full scenario at Paperkite (S08) where the player builds the control plane and data plane on the network diagram. Physical security is a Place beat on the floor plan with a simulated intrusion (S10, S37). Deception is set up by the player in S17 and pays off in S35 when Tidewater touches a honeytoken.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Confidentiality | S01, S06 | Each client's crown-jewel data named by its CIA concern | Encryption mainly protects which part of the CIA triad? → Confidentiality |
| Integrity | S06, S03 | Hash comparison in the sandbox | Hashing a file to detect changes protects ______. → Integrity |
| Availability | S06, S22, S36 | Clinic EHR uptime, DDoS | Redundant power and backups mainly protect ______. → Availability |
| Non-repudiation | S04 | Sign an email with the player's new key; recipient verifies | Which property means a sender cannot deny having sent a signed message? → Non-repudiation |
| AAA: authentication of people | S01 | MFA enrollment | Proving you are who you claim to be is ______. → Authentication |
| AAA: authentication of systems | S04, S11 | Device certificates for Wi-Fi 802.1X | Devices proving their identity with certificates is authentication of ______. → Systems |
| AAA: authorization models | S01, S08 | Group-based access to SOC tools | Deciding what an authenticated user may do is ______. → Authorization |
| AAA: accounting | S01, S17 | Login records in the SIEM | Logging what a user did, and when, is ______. → Accounting |
| Gap analysis | S02, S26 | Compare Lantern's lobby against its physical standard | Comparing current state to a desired framework to find missing controls is a ______. → Gap analysis |
| Zero trust: control plane | S08 | Place the policy engine and policy administrator on the diagram | Which zero trust plane makes access decisions? → Control plane |
| ZT: adaptive identity | S08 | Configure risk-based sign-in (new device + new country = step-up MFA) | Changing authentication requirements based on context and risk is ______. → Adaptive identity |
| ZT: threat scope reduction | S08 | Remove standing access to production | Limiting each user's reach to shrink the blast radius is ______. → Threat scope reduction |
| ZT: policy-driven access control | S08 | Write a conditional access policy | Access decided by centrally defined rules is ______. → Policy-driven access control |
| ZT: policy administrator | S08 | Diagram placement | The zero trust component that tells the enforcement point to allow or end a session → Policy administrator |
| ZT: policy engine | S08 | Diagram placement | The zero trust component that makes the trust decision → Policy engine |
| ZT: data plane | S08 | Diagram: where traffic actually flows | Which zero trust plane carries traffic and enforces decisions? → Data plane |
| ZT: implicit trust zones | S08 | Discover that Paperkite's office Wi-Fi trusts everything inside it | Zero trust aims to shrink or remove ______ zones. → Implicit trust |
| ZT: subject/system | S08 | Tag the user and the laptop requesting access | In zero trust, the user or device requesting access is the ______. → Subject |
| ZT: policy enforcement point | S08 | Place the access proxy in front of apps | The component that allows, monitors and ends connections → Policy enforcement point (PEP) |
| Bollards | S10 | Place them to block a vehicle path; a truck test-drives the gap | Posts that stop vehicles from reaching a building are ______. → Bollards |
| Access control vestibule | S10, T09 | Place it at the lobby; a tailgater is stopped | Two doors where only one opens at a time, to stop tailgating → Access control vestibule (mantrap) |
| Fencing | S10, S37 | Place the fence line; height and type trade-offs | The most common perimeter physical control around a site → Fencing |
| Video surveillance | S10 | Place cameras; coverage cones are simulated | Cameras that record an intruder are deterrent and ______. → Detective |
| Security guard | S01, S10 | Walt; decide where a guard post goes | Which physical control can make judgment calls and respond? → Security guard |
| Access badge | S01, S37 | Badge in; later a cloned badge | A card carried to open doors and show identity → Access badge |
| Lighting | S10 | Place lights; camera image quality changes | Good lighting is both a deterrent and helps ______ controls work. → Detective (cameras) |
| Sensors: infrared | S10, S37 | Place, see what triggers it | Which sensor detects body heat? → Infrared |
| Sensors: pressure | S10 | Place under the fence-line gravel | Which sensor detects weight on a floor or ground? → Pressure |
| Sensors: microwave | S10 | Place covering the yard; triggers through a thin wall | Which motion sensor sends signals and measures the reflection, and can pass through some walls? → Microwave |
| Sensors: ultrasonic | S10 | Place in the pump room | Which sensor uses high-frequency sound to detect motion? → Ultrasonic |
| Honeypot | S17, S35 | Deploy a fake server in Harbor's network | A decoy system to attract and study attackers → Honeypot |
| Honeynet | S35 | Deploy a decoy OT segment at Brightwater | A network of decoy systems → Honeynet |
| Honeyfile | S24 | Plant "Executive_Salaries.xlsx" on a Copperline share | A decoy file that alerts when opened → Honeyfile |
| Honeytoken | S35 | Plant a fake service account credential; Tidewater uses it | Fake data or a fake credential that alerts when used → Honeytoken |

## 1.3 Explain the importance of change management processes and the impact to security

**Teaching approach.** S07 is a full change advisory board cycle for replacing Ridgeway's end-of-life servers. The player writes the change request in the Ticketing app, presents it in the conference room, runs the change in a maintenance window, and handles what goes wrong. Theo's unapproved "quick fix" in a parallel thread breaks the county's legacy records app and shows the cost of skipping the process. Every later change in the game (T05) uses the same change request form, so the fields stay practiced.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| Approval process | S07, T05 | CAB meeting beat; changes need sign-off before the window | Who approves a significant production change? → The change advisory board (CAB) |
| Ownership | S07 | Assign the change owner field | The person accountable for a change succeeding is the change ______. → Owner |
| Stakeholders | S07 | Decide who to invite (Gloria, records staff, the app vendor) | People affected by a change who must be consulted → Stakeholders |
| Impact analysis | S07 | Fill risk and impact fields; what breaks if this fails? | Assessing what a change could break before approving it → Impact analysis |
| Test results | S07 | Test in the lab first; attach results | Before approval, a change request should include ______ from a non-production environment. → Test results |
| Backout plan | S07 | Theo's change has none and the player must improvise; the player's has one | A documented way to undo a failed change → Backout plan |
| Maintenance window | S07 | Pick a window against Ridgeway's office hours | A scheduled time when changes are allowed with least impact → Maintenance window |
| Standard operating procedure | S07, S32 | Follow the SOP checklist during the change | Step-by-step instructions for a routine task → Standard operating procedure (SOP) |
| Allow lists / deny lists | S07 | New server's application allow list blocks the legacy app until updated | A change that adds new software may require updating the application ______. → Allow list |
| Restricted activities | S07 | The change scope forbids touching the election server | Actions a change explicitly may not include → Restricted activities |
| Downtime | S07 | Announce and measure it | Change requests must state the expected ______ so users can plan. → Downtime |
| Service restart | S07 | `systemctl restart` drops active sessions | Restarting a service during a change can cause ______. → Brief outages or dropped sessions |
| Application restart | S07 | The records app needs a restart to read the new config | Config changes often take effect only after an application ______. → Restart |
| Legacy applications | S07, S13 | The records app only runs on an old runtime | Older apps that may break when the platform changes → Legacy applications |
| Dependencies | S07 | The records app depends on a database that depends on the old domain controller | A service that relies on another service has a ______. → Dependency |
| Updating diagrams | S07 | Update the network diagram in Docs afterwards | After a change, network ______ must be updated. → Diagrams |
| Updating policies/procedures | S07, S23 | Update the SOP to match | After a change, update ______ and ______ that describe the old setup. → Policies, procedures |
| Version control | S07, S12 | Config files and IaC tracked in a repo; roll back a bad commit | Tracking changes to code and configuration over time → Version control |

## 1.4 Explain the importance of using appropriate cryptographic solutions

**Teaching approach.** S04 sets up the player's own crypto (disk encryption, key pair, certificate, password manager). S33 runs a PKI incident at Copperline. The **Crypto Workbench** app lets the player see each primitive work: hash two files, salt and stretch a password, sign and verify, hide text in an image, tokenize a card number. Cards carry the long list of algorithms and key lengths.

| Concept | Scenarios | How it is taught | Example card |
|---------|-----------|------------------|--------------|
| PKI: public key | S04 | Publish the player's public key to the directory | Which key do you share so others can encrypt to you or verify your signature? → Public key |
| PKI: private key | S04 | Store in TPM-backed store; never exported | Which key must never be shared? → Private key |
| PKI: key escrow | S33 | Copperline requires escrow for encryption keys | A trusted third party holding copies of keys for recovery → Key escrow |
| Encryption level: full-disk | S04, T07 | Enable FDE on the player's laptop | Encrypting an entire drive, including the OS → Full-disk encryption (FDE) |
| Partition | S04 | Encrypt only the data partition on a shared lab machine | Encrypting one section of a disk → Partition encryption |
| File | S04 | Encrypt one file in Files | Encrypting individual files → File encryption |
| Volume | S04 | Encrypt a mounted volume | Encrypting a logical volume that may span disks → Volume encryption |
| Database | S33 | Turn on transparent database encryption | Encrypting the whole database at rest → Database encryption |
| Record | S33 | Encrypt only the SSN column/rows | Encrypting individual rows or fields → Record-level encryption |
| Transport/communication | S04, S19 | See cleartext vs TLS in the Packet Viewer | Protecting data in transit with TLS or IPsec is ______ encryption. → Transport/communication |
| Asymmetric | S04 | Key pair generation | Encryption using a key pair → Asymmetric |
| Symmetric | S04 | Encrypt a file with a shared key | Encryption using one shared key; faster for bulk data → Symmetric |
| Key exchange | S04, S33 | Packet Viewer shows a TLS handshake | How do two parties agree on a symmetric key over an insecure channel? → Key exchange (e.g., Diffie-Hellman) |
| Algorithms | S04, S33 | Pick algorithms in the cert request and cipher config (AES, RSA, ECC, SHA-2) | A common symmetric block cipher → AES |
| Key length | S33 | Reject a 1024-bit RSA request | Longer keys generally give ______ but cost performance. → Stronger security |
| Tools: TPM | S04 | BitLocker-style FDE sealed to the TPM | A chip on the motherboard that stores keys and supports secure boot → TPM |
| Tools: HSM | S33 | Copperline's card-signing keys live in an HSM | A dedicated, often network-attached, hardware device for managing keys at scale → HSM |
| Tools: key management system | S12, S33 | Cloud KMS for Paperkite secrets | A service that creates, stores, rotates and controls access to keys → KMS |
| Tools: secure enclave | S11 | Phone's secure enclave holds biometric templates | A protected area of a processor that isolates sensitive data → Secure enclave |
| Obfuscation: steganography | S24 | Dale hides data in images; Crypto Workbench reveals it | Hiding data inside another file, like an image → Steganography |
| Obfuscation: tokenization | S33 | Replace card numbers with tokens | Replacing sensitive data with a non-sensitive substitute that maps back via a vault → Tokenization |
| Obfuscation: data masking | S33, S26 | Show only last 4 digits to call center | Hiding part of data, like showing only the last 4 digits → Data masking |
| Hashing | S03, S21 | `sha256sum` evidence and files | A one-way function producing a fixed-length digest → Hashing |
| Salting | S04 | Workbench: same password, different salts, different hashes | Adding random data to a password before hashing to defeat rainbow tables → Salting |
| Digital signatures | S04, S34 | Sign email; verify a vendor update | A hash encrypted with the sender's private key → Digital signature |
| Key stretching | S04 | Workbench: PBKDF2/bcrypt iterations slow brute force | Making a weak key stronger by hashing it many times → Key stretching |
| Blockchain | S26 | Paperkite's audit-log product pitch | A distributed, append-only chain of hashed blocks → Blockchain |
| Open public ledger | S26 | Same | A ledger anyone can read and verify → Open public ledger |
| Certificate authorities | S04, S33 | Request a cert from Lantern's internal CA | An entity that issues and signs digital certificates → Certificate authority (CA) |
| Certificate revocation lists | S33 | Revoke a compromised cert; publish CRL | A signed list of revoked certificate serial numbers → CRL |
| OCSP | S33 | Configure OCSP stapling; compare to CRL | Checking a single certificate's status in real time → OCSP |
| Self-signed | S33 | A forgotten self-signed cert causes browser warnings | A certificate signed by its own key, not trusted by default → Self-signed |
| Third-party | S33 | Buy a public cert for the banking site | A certificate from a public CA trusted by browsers → Third-party certificate |
| Root of trust | S04, S33 | Trace a chain to the root in the cert viewer | The trusted anchor that the whole chain relies on → Root of trust |
| CSR generation | S04, S33 | `openssl req` or Certificate Manager | A request sent to a CA containing the public key and identity → Certificate signing request (CSR) |
| Wildcard | S33 | `*.copperline.example` cert; discuss risk if stolen | A certificate valid for all subdomains of one domain → Wildcard |

**Checked tasks.** S04: produce a CSR with the right subject and key size, install the issued cert, send a signed email the recipient verifies. S33: revoke the leaked cert, confirm the OCSP responder reports it revoked, reissue with a stronger key, and remove weak cipher suites.
