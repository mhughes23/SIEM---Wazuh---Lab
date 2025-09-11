# Project 5: Custom Syslog Message & Wazuh Rule Creation

## Objective
This project demonstrates the creation of **custom Wazuh rules** for detecting organization-specific events.  
**Use Case:** Detect new user account creation on a Linux/Ubuntu agent and map it to MITRE ATT&CK for SOC analysis.

---

## Requirements
- **Wazuh Manager** installed and running
- **Ubuntu agent** connected to the Wazuh Manager
- Access to `local_rules.xml` for custom rule creation
- Basic knowledge of syslog and Linux commands

---

## Steps Taken

### Step 1: Select Use Case
- Event chosen: **New user creation** on Ubuntu
- Goal: Trigger an alert when a new user is added

### Step 2: Generate Test Event
1. On the Ubuntu agent:
    ```bash
    sudo useradd hackeruser
    ```
2. Verify that the event is captured in logs:
    ```bash
    tail -f /var/log/auth.log
    ```
    **Sample Output:**
    ```
    Aug 28 12:01:23 ubuntu sudo: useradd[1234]: new user: name=hackeruser
    ```

**Screenshot:**  
![Syslog Capture](screenshots/syslog_capture.png)

---

### Step 3: Access Wazuh Custom Rules
1. Navigate to **Wazuh Dashboard → Server Management → Rules**
2. Open **`local_rules.xml`** for editing

**Screenshot:**  
- command being executed(useradd)
<img width="1710" height="1112" alt="project 5 - 1" src="https://github.com/user-attachments/assets/769c954c-9ef5-45c4-a8e0-b920da5b4dae" />

-![Local Rules Access](screenshots/local_rules_access.png)
<img width="1710" height="1112" alt="project 5 - 2" src="https://github.com/user-attachments/assets/95bf5079-6b6d-45f9-a85d-2227be3b6de2" />

- the alert 
<img width="1710" height="1112" alt="project 5 - 3" src="https://github.com/user-attachments/assets/2a94714e-1940-4d1c-80ce-130e3e1cd946" />

### Step 4: Add Custom Rule
Insert the following XML inside `local_rules.xml`:

```xml
<group name="custom,syslog,account_creation,persistence,">
  <rule id="100001" level="10">
    <if_sid>5902</if_sid>
    <description>Suspicious new user account created</description>
    <mitre>
      <id>T1136</id> <!-- MITRE ATT&CK: Create Account -->
    </mitre>
  </rule>
</group>
