# Week 5 – Advanced Security & Monitoring (Access Control, Updates, Fail2ban, Baseline & Monitoring Scripts)

---

## 1. Introduction

Week 5 implements **advanced security controls** and **monitoring capability** on the Ubuntu Server.  
This week focuses on improving the security posture through:

- **Mandatory Access Control (MAC)** using **AppArmor**
- **Automatic security updates** using unattended-upgrades
- **Intrusion protection** using fail2ban (SSH hardening)
- **Security baseline verification script** (executed on the server)
- **Monitoring output and metrics collection** (stored on the server)

All tasks are executed using terminal-based administration on the server and are evidenced through screenshots.

---

## 2. Objectives

The objectives for Week 5 are:

1. Implement Access Control using **AppArmor** and document how to check and report its status  
2. Configure **automatic security updates**  
3. Install and configure **fail2ban** for SSH intrusion protection  
4. Create and execute **security-baseline.sh** on the server  
5. Generate monitoring output files on the server and define a monitoring plan  

---

## 3. Baseline: Users and Groups (Initial State)

Before applying advanced security controls, existing users and groups are listed as baseline evidence.

### Screenshot Evidence

- **Existing Users:** `1_week5_existing_users.png`  
- **Existing Groups:** `2_week5_existing_groups.png`  

This establishes the system state before introducing additional security controls.

---

## 4. Account & Group Access Control (Role-Based)

A controlled permission model is created using a test user and a dedicated access group, demonstrating **authorisation through group membership**.

### Evidence

- **User created:** `3_week5_user_created.png`  
- **Group created:** `4_week5_group_created.png`  
- **User added to group:** `5_week5_user_added_to_group.png`  
- **Membership verified:** `6_week5_user_group_verify.png`  

---

## 5. Secure Directory & Permission Enforcement

A protected directory is created with the following controls:

- Owner: root  
- Group: secure group  
- Permissions: `770` (owner and group only)

### Evidence

- **Secure directory configured:** `7_week5_secure_directory.png`  
- **Authorised access success:** `8_week5_secure_access_success.png`  
- **Unauthorised access denied:** `9_week5_permission_denied.png`  

This demonstrates enforcement of access control boundaries.

---

## 6. Cleanup (System Restoration)

All temporary accounts, groups, and directories are removed to restore the baseline state.

### Evidence

- **Cleanup completed:** `10_week5_cleanup.png`  

---

## 7. Mandatory Access Control (MAC) – AppArmor

Ubuntu uses **AppArmor** as its Mandatory Access Control framework.  
AppArmor enforces **policy-based restrictions** on processes, even when traditional file permissions allow access.

### Verification & Reporting

The AppArmor service status and active profiles are checked using built-in tools.

### Evidence

- **AppArmor status check:** `11_week5_apparmor_status.png`  
- **AppArmor enabled evidence:** `12_week5_apparmor_enabled.png`  

---

## 8. Automatic Security Updates (unattended-upgrades)

Automatic security updates are configured to ensure the server continuously receives security patches without manual intervention, reducing exposure to known vulnerabilities.

### Evidence

- **unattended-upgrades status:** `13_week5_unattended_upgrades_status.png`  
- **Configuration evidence:** `14_week5_auto_upgrades_config.png`  

---

## 9. Intrusion Detection / Brute-Force Protection – fail2ban

fail2ban is installed and configured to protect the SSH service by detecting repeated failed login attempts and banning malicious IP addresses.

### Evidence

- **fail2ban service status:** `15_week5_fail2ban_status.png`  
- **fail2ban SSH configuration:** `16_week5_fail2ban_sshd.png`  

---

## 10. security-baseline.sh Script (Server-side Baseline Verification)

A security baseline verification script is created and executed on the server to validate core Phase 4 and Phase 5 security controls:

- SSH service state  
- Firewall status (UFW)  
- fail2ban service state  
- unattended-upgrades service state  
- AppArmor service state  
- User account listing  

### Evidence

- **Script created:** `17_week5_baseline_script_created.png`  
- **Script execution output:** `18_week5_baseline_script.png`  
- **Report saved on server:** `19_week5_baseline_script_run_and_saved.png`  
- **Saved report preview:** `20_week5_baseline_report_output.png`  

---

## 11. Monitoring Output Evidence (Server-Side Monitoring)

All monitoring data is collected **and stored on the server itself**.  
No external workstation is used for live monitoring during this phase.

### Evidence

- **Monitoring logs and status evidence:** `21_week5_ssh_status_and_logs.png`  
- **Security controls status snapshots:**  
  - `22_week5_controls_status_1.png`  
  - `23_week5_controls_status_2.png`  
- **Monitor report preview:** `24_week5_monitor_report_preview.png`  

---

## 12. Security Summary Table

| Control             | Evidence                    | Outcome                       |
|-------------------|-----------------------------|-------------------------------|
| Baseline Users      | 1_week5_existing_users.png  | Baseline captured             |
| Baseline Groups     | 2_week5_existing_groups.png | Baseline captured             |
| RBAC User/Group     | 3–6 screenshots             | Controlled authorisation      |
| Secure Directory    | 7 screenshot                | Enforced least privilege      |
| Allowed access test | 8 screenshot                | Authorised success            |
| Denied access test  | 9 screenshot                | Unauthorised blocked          |
| Cleanup             | 10 screenshot               | Returned to baseline          |
| AppArmor MAC        | 11–12 screenshots           | Verified enabled              |
| Auto Updates        | 13–14 screenshots           | Configured and verified       |
| fail2ban            | 15–16 screenshots           | SSH protection active         |
| Baseline Script     | 17–20 screenshots           | Verification automation       |
| Monitoring Output   | 21–24 screenshots           | Security & performance record |

---

## 13. Final Scripts (Appendix)

### A) `security-baseline.sh` (RUN ON SERVER)

~~~bash
#!/bin/bash
# security-baseline.sh
# Purpose: Quick verification of Phase 4 + Phase 5 security controls.
# Output: Displays and optionally saves a baseline report.

echo "===== SECURITY BASELINE CHECK ====="
echo "Date: $(date)"
echo

echo "[1] SSH Service"
systemctl is-active ssh
echo

echo "[2] Firewall (UFW) Status"
ufw status
echo

echo "[3] fail2ban Status"
systemctl is-active fail2ban
echo

echo "[4] Automatic Updates (unattended-upgrades)"
systemctl is-active unattended-upgrades
echo

echo "[5] AppArmor Status"
systemctl is-active apparmor
echo

echo "[6] User Accounts (basic list)"
cut -d: -f1 /etc/passwd
echo

echo "===== END OF REPORT ====="
~~~

**Saved on the server using:**

~~~bash
sudo bash ./security-baseline.sh | tee baseline-report.txt
~~~

---

### B) Monitoring Plan (Server-Side)

All monitoring tasks are executed **directly on the server**, and results are written to `monitor-report.txt`.

#### Metrics Collected

- CPU load and uptime  
- Memory usage  
- Disk usage  
- Active user sessions  
- Key service states (ssh, ufw, fail2ban, unattended-upgrades, apparmor)  

#### Monitoring Schedule

- During major configuration changes  
- After security updates  
- At regular administrative checkpoints  

#### Output

All results are timestamped and appended to `monitor-report.txt` on the server.

---

## 14. Reflection

Week 5 significantly strengthens the server’s security posture by enforcing **Mandatory Access Control**, automating patch management, and deploying **fail2ban** for intrusion protection.  
The baseline and monitoring scripts provide consistent, auditable verification of the system’s security state.

---

### Navigation

[Back to Index](index.md) | [Week 1](Week1.md) | [Week 2](Week2.md) | [Week 3](Week3.md) | [Week 4](Week4.md) | Week 5 | [Week 6](Week6.md) | [Week 7](Week7.md)
