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

###6. Screencshots
  - **Wazuh dashboard report
    <img width="1710" height="1112" alt="project 4 - report" src="https://github.com/user-attachments/assets/c554d32f-79ce-480b-a47a-a2bdb58581b0" />
  - **Example of new user creation
    <img width="1710" height="1112" alt="project 4 - alerts" src="https://github.com/user-attachments/assets/cee82c38-926d-467d-8a8e-fab398420525" />
  - **Custom Dashboard overview
    <img width="1710" height="1112" alt="project 4 - dashboard" src="https://github.com/user-attachments/assets/a3603a8d-7ce5-47cc-bc8f-949cc4fc174b" />
  - **MITRE ATT&CK Evidence
    <img width="1710" height="1112" alt="project 4 - mapping - new user account creation " src="https://github.com/user-attachments/assets/c21c5211-d3dd-4b7a-bfcc-0926f85a5c9e" />
    <img width="1710" height="1112" alt="project 4 - mapping - privilege escalation" src="https://github.com/user-attachments/assets/4253c691-02ea-447f-bf16-0f3abb6c745a" />
    <img width="1710" height="1112" alt="project 4 - mapping - ssh brute force" src="https://github.com/user-attachments/assets/97cb0d16-ae58-4aa5-9ef8-471eaf3701d7" />
