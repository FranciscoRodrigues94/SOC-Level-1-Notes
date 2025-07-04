# PicoSecure – TryHackMe SOC Simulation Summary

This document summarizes the detection rules and response actions configured during the PicoSecure training environment on TryHackMe. Each sample represented a different stage or technique of a cyber attack, using Pyramid of Pain, and the response was implemented using EDR, Sigma rules, firewall rules, DNS filters, or hash blocklists.

---

## Overview

| Sample       | Detection Type           | Technique             | ATT&CK ID         | Detection Focus                     |
|--------------|---------------------------|------------------------|-------------------|--------------------------------------|
| sample1.exe  | Hash Blocklist            | File-based detection   | N/A               | Prevent known malware execution     |
| sample2.exe  | Firewall Rule             | Egress Filtering       | TA0011 (C2)       | Block C2 IP communication           |
| sample3.exe  | DNS Rule                  | DNS Filtering          | TA0011 (C2)       | Block malicious domain              |
| sample4.exe  | Sigma Rule - Registry     | Defense Evasion        | TA0005            | Detect AV deactivation via registry|
| sample5.exe  | Sigma Rule - Network      | Beaconing Behavior     | TA0011 (C2)       | Detect periodic small outbound traffic|
| sample6.exe  | Sigma Rule - Process      | Data Exfiltration      | TA0010            | Detect use of temp file for data dump|

---

## Sample1.exe – Hash Detection

- **Action Taken:** Manually added the SHA1 hash to the EDR blocklist.
- **Hash Used:** `83d2791ca93e58688598485aa62597c0ebbf7610`
- **Tool:** Hash Blocklist
- **Purpose:** Prevent execution of a known malicious binary.
- **Reasoning:** Direct identification via unique file hash.


---

## Sample2.exe – Firewall Rule (Egress)

- **Action Taken:** Created firewall rule to deny outbound traffic to known C2 server.
- **Destination IP:** `154.35.10.113`
- **Rule Type:** Egress
- **Action:** Deny
- **Purpose:** Block command-and-control (C2) communication.

---

## Sample3.exe – DNS Block Rule

- **Action Taken:** Added malicious domain to DNS deny list.
- **Domain:** `emudyn.bresonicz.info`
- **Category:** Malware
- **Action:** Deny
- **Purpose:** Prevent DNS resolution of C2 domain.

---

## Sample4.exe – Registry Modification Detection

- **Action Taken:** Created Sigma Rule to detect changes to Defender settings in registry.
- **Registry Key:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Real-Time Protection`
- **Value:** `DisableRealtimeMonitoring = 1`
- **Process Responsible:** `sample4.exe`
- **EventID:** 4663
- **ATT&CK ID:** TA0005 – Defense Evasion
- **Purpose:** Detect disabling of Windows Defender via registry manipulation.

---

## Sample5.exe – Suspicious Network Behavior

- **Action Taken:** Sigma Rule created to detect repetitive, low-volume outbound connections.
- **Pattern Observed:** 97-byte packets every 1800 seconds to port 443.
- **Sample Destination:** `51.102.10.19`
- **Purpose:** Detect beaconing behavior consistent with malware calling home.
- **ATT&CK ID:** TA0011 – Command and Control

---

## Sample6.exe – Exfiltration via CMD

- **Action Taken:** Sigma Rule for process creation with suspicious exfiltration path.
- **Process Monitored:** `cmd.exe`
- **Command Line String:** `%temp%\exfiltr8.log`
- **Purpose:** Detect scripts that dump system information to a temp file.
- **ATT&CK ID:** TA0010 – Exfiltration
- **Observation:** Multiple commands writing reconnaissance output to `exfiltr8.log`.

---

## Final Notes

These actions and detection rules were created to simulate real-world SOC workflows using tools like EDR blocklists, Sigma rule logic, DNS filtering, and behavioral analysis.

