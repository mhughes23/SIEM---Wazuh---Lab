# Project 2: Log Analysis and Event Monitoring with Wazuh

## Overview
In this project, I configured Wazuh to collect and analyze logs from an Ubuntu server and macOS endpoint. 
I simulated real-world events (failed SSH logins, file modifications, and privilege escalation) to practice how SOC analysts monitor, detect, and investigate security events.

## Architecture
- **Wazuh Manager** (Ubuntu VM)
- **Wazuh Dashboard** (Web interface)
- **Agents**:
  - Ubuntu endpoint
  - macOS endpoint
- **Log Sources**:
  - SSH authentication logs
  - System logs (/var/log/syslog)
  - File integrity monitoring logs

## Steps Taken
1. **Configured Wazuh agents** on Ubuntu and macOS to forward logs to the Wazuh Manager.
2. **Verified log collection** in the Wazuh Dashboard under *Security Events → Events*.
3. **Generated test events**:
   - Failed SSH logins using `ssh invaliduser@server`.
   - File modifications in monitored directories.
   - `sudo` commands for privilege escalation logging.
4. **Analyzed alerts** by filtering logs in the dashboard:
   - Search by keyword: `ssh`, `sudo`, or `authentication failure`.
   - Filter by rule group: `authentication_failed` or `syslog`.
5. **Documented detection** by capturing screenshots of alerts in the dashboard.

## Example Alerts Observed
- **Failed SSH login**: Multiple authentication failures detected from the same IP.
- **File integrity alert**: Unauthorized modification to `/etc/passwd` test file.
- **Privilege escalation alert**: User executed a `sudo` command.

## Screenshots
- Wazuh dashboard event search
- Example SSH brute-force detection alert
- File Integrity Monitoring (FIM) alert view

## Skills Demonstrated
- Linux/macOS log collection
- Event monitoring and filtering in a SIEM
- Understanding authentication, privilege escalation, and FIM alerts
- SOC analyst workflow: *Detect → Investigate → Document*

<img width="1710" height="1112" alt="failed ssh login - project 2" src="https://github.com/user-attachments/assets/f7eb69a8-c657-4943-9f7f-a9de1b8e09c3" />
<img width="1710" height="1112" alt="FIM - roject 2" src="https://github.com/user-attachments/assets/cdace15b-8ea2-4d07-9e66-c321c20e71b6" />
<img width="1710" height="1112" alt="project 2 - sudo" src="https://github.com/user-attachments/assets/a4505545-d777-4683-a85a-3cecf6e82aa0" />
