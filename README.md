
<p align="center">
  <img
    src="https://github.com/user-attachments/assets/1f0c0a38-d39e-4ccf-acef-e015de42010f"
    width="1200"
    alt="Threat Hunt Cover Image"
  />
</p>




# 🛡️ Threat Hunt Report: Port of Entry>

---

## 📌 Executive Summary



---

## 🎯 Hunt Objectives

- Identify malicious activity across endpoints and network telemetry  
- Correlate attacker behavior to MITRE ATT&CK techniques  
- Document evidence, detection gaps, and response opportunities  

---

## 🧭 Scope & Environment
**INCIDENT BRIEF** - Azuki Import/Export - 梓貿易株式会社 

<br>
**COMPANY:** Azuki Import/Export Trading Co. - 23 employees, shipping logistics Japan/SE Asia
<br>
**EVIDENCE AVAILABLE:** Microsoft Defender for Endpoint logs
<br>
**Analyst:** Fredrick Wilson
<br>
**Date Completed:** 2026-01-067
<br>
**Environment Investigated:** Azure Logs via Microsoft Defender
<br>
**Timeframe:** 2025-11-19 -> 2025-11-20
<br>

---

## 📚 Table of Contents

- [🧠 Hunt Overview](#-hunt-overview)
- [🧬 MITRE ATT&CK Summary](#-mitre-attck-summary)
- [🔍 Flag Analysis](#-flag-analysis)
  - [🚩 Flag 1](#-flag-1)
  - [🚩 Flag 2](#-flag-2)
  - [🚩 Flag 3](#-flag-3)
  - [🚩 Flag 4](#-flag-4)
  - [🚩 Flag 5](#-flag-5)
  - [🚩 Flag 6](#-flag-6)
  - [🚩 Flag 7](#-flag-7)
  - [🚩 Flag 8](#-flag-8)
  - [🚩 Flag 9](#-flag-9)
  - [🚩 Flag 10](#-flag-10)
  - [🚩 Flag 11](#-flag-11)
  - [🚩 Flag 12](#-flag-12)
  - [🚩 Flag 13](#-flag-13)
  - [🚩 Flag 14](#-flag-14)
  - [🚩 Flag 15](#-flag-15)
  - [🚩 Flag 16](#-flag-16)
  - [🚩 Flag 17](#-flag-17)
  - [🚩 Flag 18](#-flag-18)
  - [🚩 Flag 19](#-flag-19)
  - [🚩 Flag 20](#-flag-20)
- [🚨 Detection Gaps & Recommendations](#-detection-gaps--recommendations)
- [🧾 Final Assessment](#-final-assessment)
- [📎 Analyst Notes](#-analyst-notes)

---

## 🧠 Hunt Overview
Competitor undercut our 6-year shipping contract by exactly 3%. Our supplier contracts and pricing data appeared on underground forums.

---

## 🧬 MITRE ATT&CK Summary

| Flag | Technique Category | MITRE ID | Priority |
|-----:|-------------------|----------|----------|
| 1 | <Placeholder> | <Placeholder> | <Placeholder> |
| 2 | <Placeholder> | <Placeholder> | <Placeholder> |
| 3 | <Placeholder> | <Placeholder> | <Placeholder> |
| 4 | <Placeholder> | <Placeholder> | <Placeholder> |
| 5 | <Placeholder> | <Placeholder> | <Placeholder> |
| 6 | <Placeholder> | <Placeholder> | <Placeholder> |
| 7 | <Placeholder> | <Placeholder> | <Placeholder> |
| 8 | <Placeholder> | <Placeholder> | <Placeholder> |
| 9 | <Placeholder> | <Placeholder> | <Placeholder> |
| 10 | <Placeholder> | <Placeholder> | <Placeholder> |
| 11 | <Placeholder> | <Placeholder> | <Placeholder> |
| 12 | <Placeholder> | <Placeholder> | <Placeholder> |
| 13 | <Placeholder> | <Placeholder> | <Placeholder> |
| 14 | <Placeholder> | <Placeholder> | <Placeholder> |
| 15 | <Placeholder> | <Placeholder> | <Placeholder> |
| 16 | <Placeholder> | <Placeholder> | <Placeholder> |
| 17 | <Placeholder> | <Placeholder> | <Placeholder> |
| 18 | <Placeholder> | <Placeholder> | <Placeholder> |
| 19 | <Placeholder> | <Placeholder> | <Placeholder> |
| 20 | <Placeholder> | <Placeholder> | <Placeholder> |

---

## 🔍 Flag Analysis

_All flags below are collapsible for readability._

---

<details>
<summary id="-flag-1">🚩 <strong>Flag 1: INITIAL ACCESS - Remote Access Source</strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-2">🚩 <strong>Flag 2: INITIAL ACCESS - Compromised User Account <Technique Name> </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-3">🚩 <strong>Flag 3: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-4">🚩 <strong>Flag 4: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-5">🚩 <strong>Flag 5: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-6">🚩 <strong>Flag 6: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-7">🚩 <strong>Flag 7: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-8">🚩 <strong>Flag 8: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-9">🚩 <strong>Flag 9: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-10">🚩 <strong>Flag 10: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-11">🚩 <strong>Flag 11: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-12">🚩 <strong>Flag 12: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-13">🚩 <strong>Flag 13: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-14">🚩 <strong>Flag 14: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-15">🚩 <strong>Flag 15: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-16">🚩 <strong>Flag 16: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-17">🚩 <strong>Flag 17: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-18">🚩 <strong>Flag 18: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-19">🚩 <strong>Flag 19: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

<details>
<summary id="-flag-20">🚩 <strong>Flag 20: INITIAL ACCESS - Compromised User Account </strong></summary>

### 🎯 Objective
Remote Desktop Protocol connections leave network traces that identify the source of unauthorised access. Determining the origin helps with threat actor attribution and blocking ongoing attacks.

### 📌 Finding
<High-level description of the activity>

### 🔍 Evidence

| Field | Value |
|------|-------|
| Host | <Placeholder> |
| Timestamp | <Placeholder> |
| Process | <Placeholder> |
| Parent Process | <Placeholder> |
| Command Line | <Placeholder> |

### 💡 Why it matters
The IP 88.97.178.12 is the external address the attacker used to connect via Remote Desktop Protocol (RDP). Pinpointing this source gives defenders a clear starting point: they can block the IP at the firewall, check threat intel to see if it’s linked to known actors or proxy services, and correlate it with other incidents. Knowing the exact entry vector speeds up containment and helps answer “who might be behind this?” (MITRE ATT&CK T1133 – External Remote Services).

### 🔧 KQL Query Used
DeviceLogonEvents

| where LogonType == "RemoteInteractive"

| project Timestamp, DeviceName, ActionType, RemoteIP, RemoteIPType, LogonType

| sort by Timestamp asc


### 🖼️ Screenshot
<img width="975" height="788" alt="image" src="https://github.com/user-attachments/assets/0f94a861-9bac-46ac-918d-1e9a8a8a5ac5" />

### 🛠️ Detection Recommendation

**Hunting Tip:**  
<Actionable guidance for defenders>

</details>

---

## 🚨 Detection Gaps & Recommendations

### Observed Gaps
- <Placeholder>
- <Placeholder>
- <Placeholder>

### Recommendations
- <Placeholder>
- <Placeholder>
- <Placeholder>

---

## 🧾 Final Assessment

<Concise executive-style conclusion summarizing risk, attacker sophistication, and defensive posture.>

---

## 📎 Analyst Notes

- Report structured for interview and portfolio review  
- Evidence reproducible via advanced hunting  
- Techniques mapped directly to MITRE ATT&CK  

---
