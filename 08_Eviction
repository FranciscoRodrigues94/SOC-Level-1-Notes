# APT28 – MITRE ATT&CK Navigator Analysis

This TryHackMe room simulates a real-world scenario where I (acting as a SOC Analyst named Sunny) must analyze threat intelligence related to **APT28**, a known Advanced Persistent Threat group. The organization in question, **E-Corp**, manufactures rare earth metals and could be a target due to its government and non-government contracts.

The task is to use the **MITRE ATT&CK Navigator** to identify APT28’s known techniques and answer investigative questions to detect whether the attacker has already infiltrated the network, and how to stop them.

---

## Questions & Answers

| Goal                                                                                      | Correct Answer                                |
|-------------------------------------------------------------------------------------------|-----------------------------------------------|
| Technique used by APT28 to perform both recon and initial access                          | `Spearphishing link`                          |                               
| Accounts the APT may compromise while developing resources                                | `Email accounts`                              |                               
| Execution techniques after tricking the user                                              | `Malicious file and malicious link`           |                 
| Scripting interpreters that indicate successful execution                                 | `Powershell and Windows Command shell`        |                  
| Registry keys likely modified for persistence                                             | `Registry run keys`                           |                                 
| System binary used for proxy execution                                                    | `rundll32`                                    |                                
| Tool found on host indicating network discovery                                           | `Network sniffing`                            |                                   
| Remote service exploited for lateral movement                                             | `SMB/Windows Admin shares`                    |                              
| Likely target information repository                                                      | `Sharepoint`                                  |                                  
| Proxy types used for C2 or exfiltration attempts                                          | `external proxy and multi-hop proxy`          |          

---

## Tools & References

- [MITRE ATT&CK Navigator](https://static-labs.tryhackme.cloud/sites/eviction/)
- Threat Group: [APT28 (Fancy Bear)](https://attack.mitre.org/groups/G0007/)

---

## What did I learn from this?

## What did I learn from this?

- **Practical MITRE Mapping**: I practiced mapping threat intelligence reports directly to the MITRE ATT&CK matrix, which is a vital skill for any SOC Analyst or Threat Hunter.
- **Behavior over Signatures**: I learned to focus on **TTPs (Tactics, Techniques, Procedures)** rather than static indicators. Understanding how an APT operates helps detect unknown or evolving threats.
- **Common Tools for Obfuscation & Execution**: Rundll32, PowerShell, and Windows Command Shell are key binaries attackers abuse for stealth. Knowing this helps in log analysis and alert tuning.
- **Persistence Techniques**: Simple registry key changes can ensure long-term attacker presence. These subtle tactics must not be overlooked.
- **C2 Evasion Techniques**: Attackers often use external and multi-hop proxies to mask exfiltration – knowing this helps in detecting anomalies in outbound network traffic.
