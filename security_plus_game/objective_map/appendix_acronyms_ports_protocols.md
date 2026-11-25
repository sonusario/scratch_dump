# Appendix: acronyms, ports and protocols

[Back to the map](README.md)

The SY0-701 objectives end with a list of several hundred acronyms and a list of hardware, software and tools candidates should know. They are not tied to one objective, so the game teaches them in three ways.

## 1. Acronyms everywhere in the UI

Every acronym in the game (in dialogue, app menus, logs, documents) is underlined. Hovering or long-pressing shows its expansion. The first time the player hovers an acronym, it becomes a **new card** in the Acronyms sub-deck (if they have room in today's new-card allowance), with both directions as siblings:

- `What does SASE stand for?` → Secure access service edge
- `Acronym for "secure access service edge"?` → SASE

Acronyms the player never hovers are introduced by the **coverage pass** in the last 21 days before an exam date, or in Free Shift.

## 2. The acronym chore

When acronym cards are due, they appear as the **"label maker" chore**: Walt is relabeling the server room and asks what each abbreviation on the old labels means. It is a quick round of typed or basic cards.

## 3. Reuse of the existing deck

flashcard_app's Combined deck has an **Acronyms** sub-deck covering the list. The game imports it (see [content pipeline](../07_content_model_and_pipeline.md#reusing-the-existing-security-decks)) and tags each card with the objectives where the acronym is used, so acronym mastery also feeds objective mastery.

## Ports and protocols

Ports appear in Firewall Manager rules, `ss -tulpn` output, scanner findings and packet captures. Each port below is taught in context first, then drilled with Match and Typed cards. The **secure vs insecure pairs** are a dedicated Match card set because the exam asks for the secure replacement.

| Port | Protocol | Secure alternative | Where it is first used |
|------|----------|--------------------|------------------------|
| 20/21 | FTP | SFTP (22) or FTPS (989/990) | S14: replace FTP on Ridgeway's file server |
| 22 | SSH, SCP, SFTP | | S09: jump server access |
| 23 | Telnet | SSH (22) | S09: Telnet open on a pump station switch |
| 25 | SMTP | SMTPS / STARTTLS (587, 465) | S05: email flow |
| 53 | DNS | DNS over HTTPS/TLS; DNSSEC | S36: DNS poisoning |
| 67/68 | DHCP | | S19: DHCP logs map IP to MAC |
| 69 | TFTP | | S09: PLC config backups over TFTP |
| 80 | HTTP | HTTPS (443) | S04: cleartext login seen in Packet Viewer |
| 88 | Kerberos | | S35: ticket abuse |
| 110 | POP3 | POP3S (995) | S14 |
| 123 | NTP | NTS | S21: time sync matters for timelines |
| 143 | IMAP | IMAPS (993) | S14 |
| 161/162 | SNMP (162 traps) | SNMPv3 | S17: SNMP traps |
| 389 | LDAP | LDAPS (636) | S07: Ridgeway directory bind |
| 443 | HTTPS | | Everywhere |
| 445 | SMB | | S18: worm spreads over SMB |
| 500/4500 | IKE/IPSec NAT-T | | S16: site-to-site tunnel |
| 502 | Modbus/TCP | | S09: OT firewall rule |
| 514 | Syslog | Syslog over TLS (6514) | S17: log aggregation |
| 587 | SMTP submission | | S05 |
| 636 | LDAPS | | S07 |
| 1433 | Microsoft SQL Server | | S29 |
| 1812/1813 | RADIUS | | S11 |
| 3306 | MySQL | | S29 |
| 3389 | RDP | Via jump server / VPN only | S16: vendor RDP exposed |
| 5060/5061 | SIP / SIP over TLS | | S05: VoIP vishing |

Exact port numbers follow common usage. Where CompTIA's own study material differs, CompTIA wins.

## Hardware, software and tools

The objectives also list tools candidates should recognize. Each is either an app in the [in-game computer](../05_virtual_computer.md) or an object in the world:

| Tool | In the game |
|------|-------------|
| Protocol analyzer | Packet Viewer |
| Vulnerability scanner | Sounding |
| SIEM | Beacon |
| Network scanner / port scanner | `nmap` in the range |
| Command-line tools (`ping`, `tracert`, `nslookup`, `dig`, `netstat`, `ipconfig`, `curl`, `hping`-style, `tcpdump`) | Terminal |
| Hashing and file integrity tools | `sha256sum`, `Get-FileHash`, FIM |
| Forensics (disk imager, memory capture, write blocker) | Forensics Kit |
| Password crackers (concept only) | Crypto Workbench demo of why salts and stretching matter |
| Steganography tools | Crypto Workbench |
| Badge reader, cameras, sensors, locks | World objects in the Place view |
| HSM, TPM, smart card, security key | World objects and Certificate Manager |
| Wireless analyzer | Wireless Planner |
