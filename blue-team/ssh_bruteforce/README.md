# 🔵 SSH Brute Force Detection Lab

## 📖 Overview
This lab demonstrates how Wazuh detects a simulated SSH brute force attack.  
The configuration was **left at default (no ossec.conf modifications)** to test what Wazuh can catch out of the box.

---

## ⚡ Attack Scenario
- **Attacker Machine**: Kali Linux  
- **Target Machine**: Ubuntu Agent (monitored by Wazuh Manager)  
- **Manager**: Ubuntu Server  
- **SIEM Tool**: Wazuh  
- **Attack Tool**: Hydra  
- **Attack Goal**: Crack SSH credentials by brute forcing passwords  

---

## 🛡️ Documentation
- Wazuh SIEM detected **3,592 authentication failures** on the Ubuntu Agent.  
  ![Wazuh Dashboard](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/ssh_bruteforce/screenshots/Wazuh%20SIEM%20Dashboard.png)  

- Wazuh logs confirm that the targeted machine was the **Ubuntu Agent**, and multiple rules were triggered.  
  ![Wazuh Logs](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/ssh_bruteforce/screenshots/Wazuh%20SIEM%20Logs.png)  

### ✅ Triggered Rules
1. **Rule 2502** – Password authentication failed more than once.  
   ![Rule 2502](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/ssh_bruteforce/screenshots/Rule%202502.png)  

2. **Rule 5710** – Attempted SSH login into a nonexistent user.  
   ![Rule 5710](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/ssh_bruteforce/screenshots/Rule%205710.png)  

3. **Rule 5758** – Maximum authentication attempts reached.  
   ![Rule 5758](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/ssh_bruteforce/screenshots/Rule%205758.png)  

---

## 📌 Lessons Learned
1. The attack triggered multiple Wazuh rules by default, showing SIEM strength.
2. Useful MITRE ATT&CK mapping: T1110 – Brute Force.
3. An active defense strategy could include auto-blocking IPs after repeated failures.
