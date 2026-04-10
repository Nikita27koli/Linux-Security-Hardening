# 🛡️ Linux Security Hardening Project  
### Role-Based Access • Audit Logging • SIEM Dashboard • Persistent Controls

A complete Linux hardening project built on **Debian** with **Splunk Enterprise** for security visibility.  
Designed to demonstrate practical SOC, security engineering, and system hardening skills.

---

## ⭐ Project Summary
This project implements a **defense‑in‑depth security model** across identity, access, auditing, detection, and persistence layers.  
It enforces least‑privilege access, captures high‑fidelity security logs, and provides SIEM‑ready visibility for investigations.

---

## 🔐 Key Capabilities

### **1. Role-Based Access Control (RBAC)**
- Isolated project groups (`project-a`, `project-b`, `senior-analysts`)
- ACL‑enforced directory access using `setfacl`
- Home directories locked down (`chmod 700`)
- Prevents cross‑project data exposure

### **2. Command History Hardening**
- Role‑based HISTSIZE (10 for senior analysts, 50 for others)
- Timestamped, append‑only history for forensic accuracy
- Global enforcement via `/etc/profile.d/`

### **3. Centralized Security Logging (Rsyslog)**
- Captures:
  - SSH failures  
  - Invalid user attempts  
  - Sudo violations  
  - ACL and kernel permission denials  
- Logs stored securely in `/var/log/security/`
- Logrotate configured for 90‑day retention

### **4. Splunk Security Dashboard**
- Visualizes:
  - ACL violations  
  - Authentication failures  
  - Event trends over 24 hours  
- Logs manually ingested due to VM storage constraints

### **5. Persistent Hardening Controls**
- systemd service re‑applies ACLs at every boot
- Hardened `/tmp` mount (`noexec`, `nosuid`, `nodev`)
- Hourly ACL drift detection via cron


---

## 🛠️ Technologies Used
**Linux (Debian)** • ACLs • Rsyslog • Logrotate • Systemd • Bash • Splunk Enterprise

---

## 📁 Repository Contents
- `rsyslog/` — Security logging rules  
- `scripts/` — Boot‑time enforcement & ACL automation  
- `splunk/` — Dashboard panels & sample logs  
- `docs/` — Architecture overview & validation steps  

---

## 🚀 Outcome
A fully hardened Linux environment with **least‑privilege access**, **centralized security logging**, **SIEM visibility**, and **persistent enforcement** — mirroring real SOC and security engineering workflows.
# Linux-Security-Hardening
This project demonstrates a complete Linux hardening pipeline suitable for SOC, blue‑team, or security engineering portfolios.
