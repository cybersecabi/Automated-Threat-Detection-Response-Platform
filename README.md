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

---

## 2️⃣ Setup LimaCharlie

1. Create an account and installation key  
2. Download and install agent on Windows Server:  
   
   Command:
   lc_sensor.exe -I YOUR_INSTALLATION_KEY
   >> YOUR_INSTALLATION_KEY is the Session Key which you can find in LimaCharlie Portal
  
4. Confirm LimaCharlie Service is running in Win Server
5. Confirm the Win Server is visible under LimaCharlie Portal Sensor List

### Part 3: Generate Telemetry for Lazgne and Create D&R rules in LimaCharlie

1. Install Lazagne in Win Server
2. Download from GitHub
3. Run LaZagne and observe the process via LimaCharlie
4. Create D&R Rule in LimaCharlie Portal
5. Goto Automation
6. D&R Rules
7. New Rule (Response + Detect)
8. Test Rule by clicking on Test Event
9. Confirm logs under Detection

### Part 4: Setup and Integrate Slack & Tines

1. Create Slack channels (e.g., alerts)
2. Create an account in Tines
3. In Tines:
  4. Drag in Webhook → Retrieve detections from LimaCharlie
  5. Configure LimaCharlie output → Paste webhook URL in Detections > Output > Tines
  6. Re-run LaZagne to generate sample events
  7. Validate events are received in Tines

### Part 5: Alerting + Automated Response

1. Connect Tines with Slack:
2. Add Slack credentials and channel ID
3. Send messages with detection info

4. Connect Tines with Email:
5. Configure a test email address
6. Receive structured detection alerts

7. Add User Prompt:
8. Select Page in Tines and Edit Page with Heading: Dipak SOC Lab SOAR-EDR
9. Content: Do you want to isolate the Machine?
10. Add Boolean for Yes or No
11. Add Button for Submit

🧪 Final Test Results
✅ Slack alerts received with full detection context

✅ Email alerts delivered

✅ User Prompt in Tines functional

✅ LimaCharlie successfully isolated the machine when prompted

✅ End-to-end Playbook execution verified


🧠 Takeaways
Developed an end-to-end SOAR-EDR workflow from scratch

Built custom detection and automated response logic

Integrated multiple platforms to simulate a real-world SOC environment

✍️ Author
Abisath Anton Baby Sabeena
   
   
