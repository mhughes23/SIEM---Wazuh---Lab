Suricata + Wazuh Integration for Network Threat Detection
📌 Project Overview

This project demonstrates how to integrate Suricata, a Network Intrusion Detection System (NIDS), with Wazuh SIEM to enhance threat detection capabilities.

By combining Suricata's network traffic inspection with Wazuh's log analysis and alerting, this setup provides a comprehensive security monitoring solution that detects, analyzes, and visualizes malicious activity in real time.
🛠️ Infrastructure
Component	Description
Ubuntu 22.04	Host system where Suricata is installed. Wazuh monitors the Suricata logs to generate alerts.
⚙️ Configuration Steps
1. Install Suricata
bash

sudo add-apt-repository ppa:oisf/suricata-stable
sudo apt-get update
sudo apt-get install suricata -y

2. Configure Suricata & Wazuh

    -Applied Emerging Threats ruleset for intrusion detection
    -Configured /etc/suricata/suricata.yaml to monitor the correct network interface
    -Updated Wazuh agent configuration to parse Suricata JSON logs
    -Restarted services to apply changes

3. Attack Emulation & Detection

    -Test: Simulated a ping flood against the monitored endpoint
    -Detection: Suricata captured the traffic in /var/log/suricata/eve.json
    -Alerting: Wazuh automatically parsed the logs and generated security alerts
    -Visualization: Alerts were displayed in the Wazuh Threat Hunting dashboard, with filtering options for deeper investigation

📊 Results

    -Successfully integrated Suricata NIDS with Wazuh SIEM
    -Detected and logged simulated network attacks in real time
    -Demonstrated ability to configure rules, parse network events, and visualize alerts

🚀 Skills Highlighted

    -Network Security Monitoring (Suricata, Wazuh SIEM)
    -Intrusion Detection Systems (IDS) configuration & rule management
    -Log Analysis & Threat Hunting
    -Linux System Administration (Ubuntu 22.04, systemctl, YAML/XML config)
    -Security Operations (SOC) Practices
