# Week 3 — Data Processing and Exploitation

**Tasks:** Deploy MISP and import IOCs · Apply filtering and normalization techniques

## 1. MISP Deployment

- Deployed a local/test MISP instance (Docker-based) for the team.
- Created an event: **"Meduza Stealer — Game Cheat Lure Campaign"**.
- Imported IOCs gathered in Week 2 (hashes, C2 IP:port, domains) as MISP attributes,
  tagged with `malware:Meduza-Stealer` and `tlp:white` (for this academic exercise).

## 2. Filtering & Normalization

| Step | Action |
|---|---|
| **De-duplication** | Removed IOCs already expired/retired in ThreatFox (e.g. flagged `expired`) |
| **Format normalization** | Standardized IP:port notation, defanged indicators (`62[.]60.244.198`) for safe documentation |
| **Confidence tagging** | Kept only `high confidence` IOCs from ThreatFox for the MISP import; lower-confidence pivots from Maltego marked `to-verify` |
| **Context enrichment** | Attached ATT&CK technique tags to relevant IOCs (e.g. geofencing behavior → Discovery tactic) |

## Screenshots

<!-- Place this week's screenshots in this same folder (week3/) and reference them below, e.g.: -->
<!-- ![MISP event dashboard](misp-dashboard.png) -->
<!-- ![MISP IOC import](misp-import.png) -->
