# ☁️ Cloud Log Monitoring with Wazuh

## 📌 Project Overview
This project demonstrates how I extended my **Wazuh SIEM lab** to monitor **AWS CloudTrail logs** for security events such as unauthorized logins, privilege escalation, and suspicious data access.  

The goal of this project is to showcase **SOC analyst skills in cloud security monitoring**, detection engineering, and threat hunting using **Wazuh Dashboards**.  

---

## ⚙️ Requirements
- **Wazuh SIEM** deployed on Ubuntu (Manager + Dashboard)  
- **AWS Account** with CloudTrail enabled  
- **AWS CLI** configured on the Ubuntu server  
- **S3 bucket** to store CloudTrail logs  
- Basic knowledge of **Wazuh rules & decoders**

---

## 🛠️ Steps Taken

### 1. Enable CloudTrail in AWS
- Created a **CloudTrail trail** across all regions.  
- Configured CloudTrail to deliver logs to an **S3 bucket** (`wazuh-cloudtrail-logs`).  
- Verified that API activity (logins, IAM changes, S3 access) was being logged.  

📸 *[Screenshot: AWS Console showing CloudTrail enabled]*  

---

### 2. Configure Wazuh to Collect AWS Logs
On the Wazuh Manager, I enabled the AWS S3 module in `/var/ossec/etc/ossec.conf`:

```xml
<module name="aws-s3">
  <aws-s3>
    <bucket>wazuh-cloudtrail-logs</bucket>
    <aws_profile>default</aws_profile>
    <type>cloudtrail</type>
  </aws-s3>
</module>

