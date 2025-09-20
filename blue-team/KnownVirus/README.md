# 🔵 SSH Brute Force Detection Lab

## 📖 Overview
This lab demonstrates how Wazuh SIEM will alert us about detection of malware in one of our agent.
There is a slight tweak on **Wazuh SIEM's ossec.conf** to make it able to take it logs from **Windows Defender.**

---

## ⚡ Attack Scenario
- **Attacker Machine**: Windows Agent (Self attack)  
- **Target Machine**: Windows Agent (monitored by Wazuh Manager)  
- **Manager**: Ubuntu Server  
- **SIEM Tool**: Wazuh  
- **Attack Tool**: EICAR 
- **Attack Goal**: Spreading malware

---

## 🛡️ Documentation
- EICAR file creation **(The malware)**
  ![EICAR File}()

- Running the EICAR file
  ![Opening the EICAR file]()

- Configuring the ossec.conf to enable it to take logs from **Windows Defender.**
  ![ossec.conf changes]()

- Wazuh logs detects installation of potential **malware** on Windows Agent.
  ![Wazuh Logs]()

-Double check the logs with **Windows Defender logs.**
  ![Windows Defender Logs]()

### ✅ Triggered Rules
1. **Rule 62123** - Installation of Potential Malware
   ![Rule 62123]()

   ---

## 📌 Lessons Learned
1. Wazuh SIEM can be configured to take logs from Anti Virus softwares
2. Installation of Anti Virus software is a must to keep the devices safe from malwares.
