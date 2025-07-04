# Standards and Frameworks in Cyber Threat Intelligence

## Overview

Standards and frameworks in threat intelligence provide **structure**, **common language**, and **cooperation** across organizations and sectors. 
They support collaboration, streamline investigations, and improve overall incident response by defining models for describing, sharing, and analyzing threats.

---

## Key Concepts

### ➤ MITRE ATT&CK
- A **knowledge base** of adversary tactics, techniques, and procedures (TTPs).
- Helps analysts track adversary behavior through mapped-out attack phases.
- Widely adopted for threat detection, hunting, and red/blue team exercises.

### ➤ TAXII (Trusted Automated eXchange of Indicator Information)
- A **protocol** to securely and automatically exchange threat intel.
- Enables near real-time sharing and response to threats.
- Two models:
  - **Collection**: Request-response model where users query threat data.
  - **Channel**: Publish-subscribe model where updates are pushed to subscribers.

### ➤ STIX (Structured Threat Information Expression)
- A **language** for standardizing and structuring threat intelligence.
- Captures observables, indicators, TTPs, campaigns, relationships, and more.
- Commonly paired with TAXII to enable structured and automated intel sharing.

### ➤ Cyber Kill Chain (by Lockheed Martin)
- A **model** outlining the sequential stages of a cyber attack:
  1. Reconnaissance  
  2. Weaponization  
  3. Delivery  
  4. Exploitation  
  5. Installation  
  6. Command and Control (C2)  
  7. Actions on Objectives  
- Helps analysts map activity to specific stages for better response.
- Extended by frameworks like ATT&CK into the **Unified Kill Chain**.

### ➤ The Diamond Model
- A model for **intrusion analysis** focused on:
  - **Adversary**: Who is behind the attack?
  - **Victim**: Who/what is being targeted?
  - **Infrastructure**: What systems/tools are being used?
  - **Capabilities**: What means (TTPs) are being leveraged?
- Encourages **pivoting** across elements to correlate IOCs and track adversary campaigns.

---

## Personal Notes

- ATT&CK is my favorite so far — very practical for understanding **real-world attack methods**.
- The **Diamond Model** helps visualize the relationships in an attack — useful to understand *how everything connects*.
- STIX + TAXII seem complex, but essential for automating large-scale intel sharing in bigger environments.
- Kill Chain reminds me of a timeline — good for breaking down incidents step by step.

---

## Learned from: TryHackMe – SOC Level 1, Room "Intro to Cyber Threat Intel"
