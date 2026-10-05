# HTB Brutus - Sherlock Investigation

A write-up and investigation record for the **Brutus** Sherlock challenge from Hack The Box.

## Overview

This repository documents the investigation process used to analyze the Brutus incident, including authentication log analysis, command execution analysis, MITRE ATT&CK mapping, and the final findings.

## Challenge

**Platform:** Hack The Box  
**Challenge:** Brutus  
**Category:** Sherlock / DFIR  
**Focus:** Log Analysis, Incident Response, Authentication Analysis, MITRE ATT&CK

## Investigation Evidence

### 01 — Brutus Challenge
The Hack The Box Brutus Sherlock overview and scenario.

### 02 — Authentication Log Analysis
Authentication and SSH activity from `auth.log`, including failed attempts and the successful root login from `65.2.161.68`.

### 03 — MITRE ATT&CK
MITRE ATT&CK mapping for the persistence activity: **T1136.001 — Create Account: Local Account**.

### 04 — Command Analysis
Command execution evidence from `auth.log`, including privileged commands and the `curl` download.

### 05 — Completed Tasks
Validated Sherlock task answers, including the first SSH session end time and the privileged download command.

### 06 — Sherlock Completed
Final evidence showing the Brutus Sherlock was successfully solved.

> The screenshots directory contains the corresponding evidence images in the same order.

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
