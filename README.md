# Threat Hunting Project — Meduza Stealer (Malware Disguised as Game Cheats)

**Course:** Introduction to Threat Hunting (ITH), Astana IT University
**Team:** Meiram, Alikhan, Ulan
**Target malware family:** Meduza Stealer

## About the Project

Meduza Stealer is a Malware-as-a-Service (MaaS) information stealer targeting Windows
systems. It is marketed and sold on underground forums and Telegram channels, and is
frequently distributed disguised as game cheats, cracked software, and "free" tools —
lures that specifically target gamers. Once executed, it harvests browser data (saved
credentials, cookies, browsing history, bookmarks), cryptocurrency wallet extensions,
password manager vaults, 2FA extensions, Steam and Discord session data, and general
system information, then exfiltrates it to an attacker-controlled command-and-control
(C2) server.

Notable behavioral trait: Meduza performs a geofence check on startup and self-terminates
if the host is located in a CIS country (Russia, Kazakhstan, Belarus, etc.), and it also
refuses to run if its C2 server is unreachable — both of which complicate detection and
sandboxing.

## Repository Structure

```
README.md          ← this file — project overview
week1/notes.md      ← CTI Fundamentals: glossary + threat classification
week2/notes.md      ← Data Collection: OSINT plan, seed indicators, data source map
week3/notes.md      ← Data Processing: MISP deployment, filtering & normalization
week1/ week2/ week3/  ← also hold screenshots for that week
```

Each week's folder contains a `notes.md` with the write-up for that week, plus any
supporting screenshots placed directly alongside it.

## Sources

- Wazuh Blog — *Meduza Stealer Detection and Mitigation with Wazuh*
- SOC Prime — *MEDUZASTEALER Malware Detection*
- Security Affairs — *Meduza Stealer analysis (Uptycs research)*
- ThreatFox (abuse.ch) — IOC database entries tagged `MeduzaStealer`
- any.run — public sandbox analysis reports
- Recorded Future Sandbox — behavioral analysis report

## Weekly Commit Log

| Week | Date | Contributor | Summary of commit |
|---|---|---|---|
| 1 | | | Glossary + threat classification added |
| 2 | | | OSINT screenshots + data source map added |
| 3 | | | MISP deployment + IOC import screenshots added |

## Defense Notes (7–8 min per group)

1. What Meduza Stealer is and why it's disguised as game cheats (30s)
2. Week 1 — CTI glossary & classification (1.5 min)
3. Week 2 — OSINT tools used + what we found (2.5 min, show screenshots)
4. Week 3 — MISP setup + IOC filtering (2.5 min, show screenshots)
5. Next steps (Cyber Kill Chain mapping, Week 4) (30s)
