# Week 1 — Cyber Threat Intelligence Fundamentals

**Tasks:** Create a glossary of key CTI terms · Classify threat types and their sources

## 1. Glossary of Key CTI Terms (applied to Meduza Stealer)

| Term | Definition | Relevance to Meduza Stealer |
|---|---|---|
| **IOC (Indicator of Compromise)** | A forensic artifact (hash, IP, domain, registry key) suggesting a system has been compromised | Meduza C2 IPs, file hashes (MD5/SHA1/SHA256), dropped file names |
| **TTP (Tactics, Techniques, Procedures)** | The behavioral patterns an attacker/malware uses | Geofencing check, Defender exclusion via PowerShell, browser credential theft |
| **MaaS (Malware-as-a-Service)** | Malware sold/rented as a subscription product with a management console | Meduza is sold with monthly/lifetime plans and a stealer admin panel |
| **Stealer / Infostealer** | Malware designed to exfiltrate stored credentials and sensitive data rather than encrypt or destroy | Meduza's entire purpose — no ransomware component |
| **C2 (Command and Control)** | Server infrastructure used by the attacker to control malware and receive stolen data | Meduza checks C2 reachability before activating; exfiltrates loot here |
| **Dropper / Loader** | A file whose job is to deliver and execute the real payload | Game-cheat `.exe` / cracked installer that drops the Meduza payload |
| **Geofencing (malware)** | Malware logic that checks victim location and halts execution in excluded regions | Meduza excludes CIS countries (RU, KZ, BY, GE, TM, UZ, AM, KG, MD, TJ) |
| **Exfiltration** | The unauthorized transfer of data out of a victim system | Meduza packages stolen browser/wallet data and uploads it to its C2 |
| **OSINT** | Open Source Intelligence — information gathered from publicly available sources | Used in Week 2 to pull Meduza IOCs from VirusTotal, ThreatFox, any.run |
| **ATT&CK Technique** | A specific method mapped in the MITRE ATT&CK framework | e.g., T1555 (Credentials from Password Stores), T1082 (System Info Discovery) |

## 2. Threat Classification

| Attribute | Assessment |
|---|---|
| **Threat category** | Commodity malware — Information Stealer (non-destructive, financially motivated) |
| **Delivery vector** | Social engineering via fake game cheats / cracks / "free" tool downloads (YouTube video descriptions, Discord servers, cheat forums, cracked-software sites) |
| **Threat actor type** | Cybercriminal MaaS operator + independent affiliates/customers who buy access |
| **Motivation** | Financial — stolen credentials and wallets are resold or drained; access itself is sold as a subscription |
| **Target platform** | Windows desktop users, primarily gamers/PC enthusiasts searching for cheats |
| **Sophistication** | Low-to-moderate — binary is largely unobfuscated per public analyses, but detection rates by AV are historically poor |
| **Source of intel used** | Vendor write-ups (Uptycs, Wazuh, SOC Prime), sandbox reports (any.run), IOC feeds (ThreatFox/abuse.ch) |

## Screenshots

<!-- Place this week's screenshots in this same folder (week1/) and reference them below, e.g.: -->
<!-- ![Glossary whiteboard](glossary.png) -->
