# 🛡️ Cybersecurity SOAR-EDR Project

A complete hands-on Security Orchestration, Automation, and Response (SOAR) + Endpoint Detection and Response (EDR) lab using **Tines**, **LimaCharlie**, **Slack**, and **Email** to detect, alert, and respond to malicious activity — specifically detecting the use of the **LaZagne** credential dumping tool.

---

## 🔧 Technologies Used

- **SOAR**: [Tines](https://tines.com)
- **EDR**: [LimaCharlie](https://limacharlie.io)
- **Communication**: Slack, Email

---

## 🎯 Project Objectives

- ✅ Create custom Detection & Response rule in LimaCharlie
- ✅ Design a SOAR playbook in Tines
- ✅ Integrate Slack & Email for alerting
- ✅ Automate host isolation based on user input

---

## 1️⃣ SOAR-EDR Playbook Design

- **Detection Trigger**: LimaCharlie detects the `LaZagne` hacktool
- **Workflow**:
  1. Tines receives detection via webhook
  2. Sends alert to Slack & Email containing:
     - Time
     - Computer Name
     - Source IP
     - Command Line
     - File Path
     - Sensor ID
     - Detection Link
  3. User prompt in Tines: “Do you want to isolate the machine?”
     - **Yes** → Isolate the endpoint via LimaCharlie
     - **No** → Notify for further investigation

![Playbook Screenshot](https://github.com/user-attachments/assets/f7b53ae9-dc16-418e-83b4-ce7d4d07632f)

---

## 2️⃣ Setup LimaCharlie

1. Create an account and installation key  
2. Download and install agent on Windows Server:  
   ```bash
  <lc_sensor.exe -I YOUR_INSTALLATION_KEY>
  <
   Command:
   lc_sensor.exe -I YOUR_INSTALLATION_KEY
   >> YOUR_INSTALLATION_KEY is the Session Key which you can find in LimaCharlie Portal

   
