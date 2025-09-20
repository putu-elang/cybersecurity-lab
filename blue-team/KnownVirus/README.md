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
- Configuring the ossec.conf to enable it to take logs from **Windows Defender.**
  ![ossec.conf changes](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/KnownVirus/Screenshots/XML%20addition%20for%20%20windows%20%20defender%20log.png)

- EICAR file creation **(The malware)**
  ![EICAR File](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/KnownVirus/Screenshots/EICAR%20string.png)

- Running the EICAR file
  ![Opening the EICAR file](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/KnownVirus/Screenshots/EICAR%20%20run.png)

- Wazuh logs detects installation of potential **malware** on Windows Agent.
  ![Wazuh Logs](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/KnownVirus/Screenshots/Wazuh%20%20Dashboard.png)

-Double check the logs with **Windows Defender logs.**
  ![Windows Defender Logs](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/KnownVirus/Screenshots/Defender%20Log.png)

### ✅ Triggered Rules
1. **Rule 62123** - Installation of Potential Malware
   ![Rule 62123](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/KnownVirus/Screenshots/Ruleset.png)

   ---

## 📌 Lessons Learned
1. Wazuh SIEM can be configured to take logs from Anti Virus softwares
2. Installation of Anti Virus software is a must to keep the devices safe from malwares.
