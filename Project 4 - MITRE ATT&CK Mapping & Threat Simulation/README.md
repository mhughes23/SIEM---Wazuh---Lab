# Project 4: MITRE ATT&CK Mapping & Threat Simulation with Wazuh

This project demonstrates how to **simulate adversary behaviors** on an Ubuntu server, generate **Wazuh alerts**, and map them to the **MITRE ATT&CK framework**. The goal is to showcase threat detection, analysis, and reporting skills relevant for SOC analyst roles.

---

## 🚀 Project Overview
- **Tooling**: Wazuh SIEM, Ubuntu agent, Wazuh dashboard
- **Focus**: Threat simulation, alert generation, MITRE ATT&CK mapping
- **SOC Relevance**: Demonstrates ability to connect logs → attacker behavior → defensive actions

---

## 🛠️ Steps Taken

### 1. Simulated Adversary Behavior on Ubuntu
Executed commands to mimic real attacker actions:

- **Brute Force SSH (T1110 – Credential Access)**  
  ```bash
  ssh invaliduser@localhost
  ssh invaliduser@localhost
  ssh invaliduser@localhost

###2. Analyzed Alerts in Wazuh
Navigated to Wazuh Dashboard → Security Events → Events.
  - **Applied filters for each type of event (SSH Brute Force, Priviliege Escalation, New User Creation)
  - **Verified that events appeared in the correct time range.
  - **Documented rule IDs, severity levels, and MITRE mappings.
    
###3. Created Visualizations
  - **Used Kibana Visualizations to convert raw event logs into insights

###4. Created a new MITRE ATT&CK Threat Simulation Dashboard.
  - **Added the three visualizations (SSH brute force, privilege escalation, new user creation).
  - **Arranged them to show failed SSH attempts trend, privilege escalation attempts by user, and User creation events.

###5. MITRE ATT&CK Mapping

  - **Mapped each alert to its MITRE ATT&CK technique for SOC analysis:

  --**Event	Rule ID	MITRE ATT&CK Technique
  --**SSH Brute Force	5710	T1110 – Brute Force
  --**Privilege Escalation (sudo)	5402	T1068 – Elevation of Privilege
  --**User Account Creation	550	T1136 – Create Account

  -Screenchots

