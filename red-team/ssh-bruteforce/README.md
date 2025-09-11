# 🔴 **SSH Brute Force Attack Lab**

## 📖 Overview
This lab simulates a brute force attack against an SSH service using **Hydra**.  
The goal is to test how brute force attack can be done in a honelab settings and how the Blue Team (Wazuh SIEM) detects this activity.

---

## ⚡ Attack Scenario
- **Attacker Machine**: Kali Linux  
- **Target Machine**: Ubuntu Agent  
- **Attack Tool**: Hydra  
- **Attack Goal**: Crack SSH credentials by brute forcing passwords  

---

## 🛠️ Attack Execution
### Step 1 – Identify Target
-For this step I know the IP of the agent because I was also the one who created it.
### Step 2 - Launch the Attack
-I proceeded with the attack towards Ubuntu Agent from my Kali using hydra
```bash
hydra -l fakeuser -P /usr/share/wordlists/rockyou.txt ssh://<Target IP>
```
[Attack Proceeding](https://github.com/putu-elang/cybersecurity-lab/blob/main/red-team/ssh-bruteforce/hydra%20command%20line.png)

---

## 📊 Results
-Hydra attempted 3,592 login attempts against the target.
-No valid credentials were cracked (username/password mismatch).
-Attack generated thousands of failed login logs in /var/log/auth.log.
[Auth Log](https://github.com/putu-elang/cybersecurity-lab/blob/main/blue-team/ssh_bruteforce/screenshots/Linux%20Auth%20Log.png)

---

##📌 Lessons Learned
1. Brute force is easy to execute but extremely noisy.
2. There are better stealth method such as password spraying or lowering the requrest rate with hydra.
3. Hydra is effective for testing detection but impractical for real stealthy attacks.
