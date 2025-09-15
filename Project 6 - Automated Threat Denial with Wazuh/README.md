# Cloud Security Monitoring & Threat Detection Project

## Overview
This project demonstrates a personal Security Operations Center (SOC) workflow for **cloud infrastructure monitoring**. Using **Wazuh SIEM** and cloud logs (AWS CloudTrail), the project simulates real-world SOC activities, including detecting misconfigurations, unauthorized access, and suspicious API activity.  

This project highlights skills relevant to a SOC analyst role: **log collection, alert creation, dashboard visualization, and incident reporting**.

---

## Requirements
- Wazuh Manager running on Ubuntu server  
- Wazuh Agent installed on a VM or cloud instance  
- Cloud account (AWS preferred for CloudTrail logging)  
- Filebeat for log forwarding to Wazuh  
- Kibana or Wazuh dashboards for visualization  

---

## Steps Taken

### 1. Cloud Log Collection
- Enabled **AWS CloudTrail** to capture all API activity.  
- Configured **Filebeat** to forward CloudTrail logs to Wazuh Manager:  
```bash
sudo apt install filebeat
