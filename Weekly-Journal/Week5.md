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

### Evidence

- **Existing Users:**  
  ![Existing Users](./Screenshots/Week5/1_week5_existing_users.png)

- **Existing Groups:**  
  ![Existing Groups](./Screenshots/Week5/2_week5_existing_groups.png)

---

## 4. Account & Group Access Control (Role-Based)

A controlled permission model is created using a test user and a dedicated access group.

### Evidence

- **User created:**  
  ![User Created](./Screenshots/Week5/3_week5_user_created.png)

- **Group created:**  
  ![Group Created](./Screenshots/Week5/4_week5_group_created.png)

- **User added to group:**  
  ![User Added](./Screenshots/Week5/5_week5_user_added_to_group.png)

- **Membership verified:**  
  ![Group Verified](./Screenshots/Week5/6_week5_user_group_verify.png)

---

## 5. Secure Directory & Permission Enforcement

A protected directory is created with:

- Owner: root  
- Group: secure group  
- Permissions: `770`  

### Evidence

- **Secure directory configured:**  
  ![Secure Directory](./Screenshots/Week5/7_week5_secure_directory.png)

- **Authorised access success:**  
  ![Access Allowed](./Screenshots/Week5/8_week5_secure_access_success.png)

- **Unauthorised access denied:**  
  ![Access Denied](./Screenshots/Week5/9_week5_permission_denied.png)

---

## 6. Cleanup (System Restoration)

Temporary accounts, groups, and directories are removed to restore the baseline state.

### Evidence

- **Cleanup completed:**  
  ![Cleanup](./Screenshots/Week5/10_week5_cleanup.png)

---

## 7. Mandatory Access Control (MAC) – AppArmor

AppArmor enforces policy-based restrictions on processes.

### Evidence

- **AppArmor status:**  
  ![AppArmor Status](./Screenshots/Week5/11_week5_apparmor_status.png)

- **AppArmor enabled:**  
  ![AppArmor Enabled](./Screenshots/Week5/12_week5_apparmor_enabled.png)

---

## 8. Automatic Security Updates

### Evidence

- **unattended-upgrades status:**  
  ![Auto Updates](./Screenshots/Week5/13_week5_unattended_upgrades_status.png)

- **Configuration:**  
  ![Auto Config](./Screenshots/Week5/14_week5_auto_upgrades_config.png)

---

## 9. Intrusion Protection – fail2ban

### Evidence

- **fail2ban status:**  
  ![fail2ban Status](./Screenshots/Week5/15_week5_fail2ban_status.png)

- **SSH protection active:**  
  ![fail2ban SSH](./Screenshots/Week5/16_week5_fail2ban_sshd.png)

---

## 10. security-baseline.sh Script

### Evidence

- **Script created:**  
  ![Script Created](./Screenshots/Week5/17_week5_baseline_script_created.png)

- **Script executed:**  
  ![Script Output](./Screenshots/Week5/18_week5_baseline_script.png)

- **Report saved:**  
  ![Saved Report](./Screenshots/Week5/19_week5_baseline_script_run_and_saved.png)

- **Report preview:**  
  ![Report Preview](./Screenshots/Week5/20_week5_baseline_report_output.png)

---

## 11. Monitoring Output (Server-side)

### Evidence

- **Logs & status:**  
  ![Logs](./Screenshots/Week5/21_week5_ssh_status_and_logs.png)

- **Controls status:**  
  ![Controls 1](./Screenshots/Week5/22_week5_controls_status_1.png)

- **Controls status:**  
  ![Controls 2](./Screenshots/Week5/23_week5_controls_status_2.png)

- **Monitor report preview:**  
  ![Monitor Preview](./Screenshots/Week5/24_week5_monitor_report_preview.png)

---

## 12. Reflection

Week 5 strengthens the server’s security posture through MAC enforcement, automated patching, and intrusion protection.  
Baseline and monitoring scripts provide consistent verification and audit-ready evidence.

---

### Navigation

[Back to Index](index.md) | [Week 1](Week1.md) | [Week 2](Week2.md) | [Week 3](Week3.md) | [Week 4](Week4.md) | Week 5 | [Week 6](Week6.md) | [Week 7](Week7.md)
