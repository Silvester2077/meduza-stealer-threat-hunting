# Week 2 — Data Collection Process

**Tasks:** Perform OSINT data collection using Shodan, VirusTotal, and Maltego ·
Develop a data source mapping for analysis

## 1. OSINT Collection Plan

| Tool | What we searched for | What we expect to find |
|---|---|---|
| **VirusTotal** | Known Meduza Stealer sample hashes, related file names (e.g. cheat-themed `.exe` names), C2 domains/IPs | AV detection ratios, sandbox behavior tags, relationship graph to other samples |
| **Shodan** | Exposed panels / open directories hosting stealer builds or logs (IP ranges seen in public write-ups) | Open-directory servers hosting `.exe` payloads, exposed stealer admin panels |
| **Maltego** | Pivoting from a known C2 IP/domain → registrar info, related infrastructure, passive DNS | Infrastructure clusters reused across Meduza campaigns |

## 2. Seed Indicators (from public sources, used as OSINT starting points)

- **Malware family tag:** `MeduzaStealer` (ThreatFox / abuse.ch)
- **Example C2 (expired, historical):** `62.60.244.198:15666` — tagged `botnet_cc`, AS210644 (AEZA), first seen 2024-11-30
- **Example sample hashes (any.run public reports):**
  - `MD5: 6A83141B90D2A675DEBC4D149A790DA0`
  - `SHA256: 8844D41002892739EE42DB2B481E67D6EDBAAA0A9B9DF5E314C2C083F2900BEE`
- **Behavioral IOC:** outbound call to `api.ipify.org` to fetch the victim's public IP before exfiltration

## 3. Data Source Mapping

```
Public Sandbox Reports (any.run, Recorded Future sandbox)
        │
        ▼
   File Hashes / C2 IPs / Domains
        │
   ┌────┴─────┬───────────────┐
   ▼          ▼               ▼
VirusTotal  Shodan          Maltego
(sample     (exposed        (infra pivoting:
verdicts,   panels/         WHOIS, passive DNS,
relations)  open dirs)      related domains)
        │          │               │
        └────┬─────┴───────────────┘
             ▼
     Consolidated IOC list
             │
             ▼
      → feeds into Week 3 (MISP import)
```

## Screenshots

<!-- Place this week's screenshots in this same folder (week2/) and reference them below, e.g.: -->
<!-- ![VirusTotal lookup](virustotal.png) -->
<!-- ![Shodan search](shodan.png) -->
<!-- ![Maltego graph](maltego.png) -->
