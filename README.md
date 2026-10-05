# HTB Brutus - Sherlock Investigation

A write-up and investigation record for the **Brutus** Sherlock challenge from Hack The Box.

## Overview

This repository documents the investigation process used to analyze the Brutus incident, including authentication log analysis, command execution analysis, MITRE ATT&CK mapping, and the final findings.

## Challenge

**Platform:** Hack The Box  
**Challenge:** Brutus  
**Category:** Sherlock / DFIR  
**Focus:** Log Analysis, Incident Response, Authentication Analysis, MITRE ATT&CK

## Investigation Workflow

1. Review the Brutus challenge information.
2. Analyze authentication and login activity.
3. Identify suspicious source addresses and account activity.
4. Correlate timestamps and events.
5. Analyze commands executed during the incident.
6. Map observed behavior to MITRE ATT&CK techniques.
7. Complete the challenge tasks and document the findings.

## Repository Structure

```text
HTB-Brutus-Sherlock/
│
├── README.md
│
├── screenshots/
│   ├── 01-brutus-challenge.png
│   ├── 02-auth-log-analysis.png
│   ├── 03-mitre-attack.png
│   ├── 04-command-analysis.png
│   ├── 05-completed-tasks.png
│   └── 06-sherlock-completed.png
│
└── notes/
    └── investigation-notes.md
```

## Skills Demonstrated

- Linux authentication log analysis
- Incident timeline reconstruction
- Suspicious login identification
- Command-line investigation
- IOC identification
- MITRE ATT&CK mapping
- DFIR methodology
- Security event correlation

## Evidence

Screenshots from the investigation are stored in the `screenshots/` directory.

Detailed investigation notes are available in:

[`notes/investigation-notes.md`](notes/investigation-notes.md)

## Disclaimer

This repository is intended for educational and portfolio purposes. The investigation was performed against the Hack The Box Sherlock challenge environment.
