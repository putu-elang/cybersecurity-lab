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
