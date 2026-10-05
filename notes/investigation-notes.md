# Investigation Notes — HTB Brutus

## 1. Challenge Overview

The **Brutus** Sherlock challenge focuses on investigating suspicious activity through system and authentication logs.

The objective is to reconstruct the incident timeline, determine how the attacker gained access, identify the affected account(s), analyze commands executed during the compromise, and associate the attacker behavior with relevant MITRE ATT&CK techniques.

---

## 2. Initial Investigation

The investigation begins by examining the available authentication-related logs and identifying unusual login behavior.

Key items to look for:

- Failed authentication attempts
- Successful authentication attempts
- Source IP addresses
- Target usernames
- Login timestamps
- Session activity
- Privilege-related activity

The goal is to establish a reliable timeline before interpreting individual events.

---

## 3. Authentication Log Analysis

Authentication events should be correlated by:

**Timestamp → Source IP → Username → Authentication result → Follow-up activity**

Repeated failed attempts followed by a successful login can indicate password-guessing or brute-force behavior.

When reviewing the logs, record:

| Evidence | Observation |
|---|---|
| Source IP | Document the suspicious source address |
| Target account | Document the affected account |
| Failed attempts | Record the relevant authentication attempts |
| Successful login | Record the first suspicious successful login |
| Timeline | Correlate the activity chronologically |

> Replace the placeholders above with the exact values from the completed challenge evidence.

---

## 4. Incident Timeline

Build the timeline from the earliest suspicious authentication event through the attacker’s command execution and subsequent activity.

Example format:

```text
[Time]  Failed authentication attempts
[Time]  Successful authentication
[Time]  Attacker session established
[Time]  Suspicious command execution
[Time]  Privilege / persistence / follow-up activity
```

The exact timestamps and events should be taken directly from the challenge evidence.

---

## 5. Command Analysis

Review commands executed during the compromised session.

Look for commands that:

- Enumerate the host
- Identify users or privileges
- Download or retrieve files
- Modify system configuration
- Establish persistence
- Execute payloads
- Hide or remove evidence

For each significant command, document:

1. The command
2. What it does
3. Why it is suspicious or relevant
4. The associated MITRE ATT&CK technique, where applicable

---

## 6. MITRE ATT&CK Mapping

Map observed attacker behavior to the appropriate MITRE ATT&CK techniques.

Potential technique categories may include:

- **Credential Access**
- **Initial Access**
- **Execution**
- **Persistence**
- **Privilege Escalation**
- **Discovery**
- **Command and Control**

Only assign a technique when the evidence supports it.

---

## 7. Investigation Findings

The final findings should summarize:

- Initial access vector
- Attacker/source IP
- Compromised account
- Important authentication events
- Commands executed
- Relevant ATT&CK techniques
- Overall incident timeline

---

## 8. Lessons Learned

This challenge reinforces the importance of:

- Monitoring authentication logs
- Detecting repeated failed logins
- Correlating successful logins with preceding failures
- Investigating unexpected source addresses
- Reviewing shell command history and process activity
- Using MITRE ATT&CK to classify attacker behavior
- Maintaining a clear incident timeline

---

## 9. Evidence Screenshots

The supporting screenshots are stored under:

```text
screenshots/
```

Expected files:

- `01-brutus-challenge.png`
- `02-auth-log-analysis.png`
- `03-mitre-attack.png`
- `04-command-analysis.png`
- `05-completed-tasks.png`
- `06-sherlock-completed.png`
