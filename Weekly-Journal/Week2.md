# 📘 Week 2 – Security Configuration & Remote Administration

---

## 1. Introduction

Week 2 focused on implementing secure remote administration and establishing a strong operating system security baseline.  
The primary objective was to configure **secure SSH access**, validate network readiness, and demonstrate **file permission and ownership enforcement** using Linux access control mechanisms.

These tasks replicate real-world server administration where systems must remain remotely accessible while strictly controlling user privileges.

---

## 2. Objectives for This Week

The main objectives of Week 2 were:

- Enable secure remote administration
- Verify SSH service availability
- Confirm correct network configuration
- Implement file permission and ownership controls
- Demonstrate user privilege separation
- Define a strong security baseline for future hardening

---

## 3. Remote Administration Overview

### Why Remote Administration Is Needed

Remote administration allows administrators to manage servers without physical access, which is the standard practice in professional environments.

**Advantages:**
- Faster system management and troubleshooting  
- Reduced downtime  
- Real-world server administration experience using SSH  

**Potential Risks:**
- Unauthorized login attempts  
- Brute-force password attacks  
- Increased network exposure  

These risks require strict operating system level security controls.

---

## 4. SSH Service Verification

The SSH service was verified using:

- `sudo systemctl status ssh`

This confirmed that the SSH daemon is active and ready for secure remote connections.

![SSH Service Running](../Screenshots/Week2/Week2_1_directory_created.png)

---

## 5. Network Configuration Verification

The network interface and IP address were verified using:

- `ip a`

This confirmed that the network interface was active, assigned an IP address, and ready for remote access.

![Network Interface & IP](../Screenshots/Week2/Week2_2_ssh_satatus.png)

---

## 6. File Permission Configuration

A test file was created and restricted:

- `touch permissions.txt`
- `chmod 700 permissions.txt`

This ensures only the owner has access, enforcing the **principle of least privilege**.

![File Permissions Applied](../Screenshots/Week2/Week2_3_network_ip.png)

---

## 7. File Ownership Enforcement

Ownership of files was verified and corrected:

- `touch ownership.txt`
- `sudo chown vboxuser:vboxuser ownership.txt`

This ensures proper access control by the operating system.

![Ownership Applied](../Screenshots/Week2/Week2_4_permissions.png)

---

## 8. User & Privilege Management

Additional user accounts were created to simulate role separation:

- `sudo adduser analyst`
- `sudo adduser auditor`

![Users Created](../Screenshots/Week2/Week2_5_ownership.png)

The analyst account was granted administrative privileges:

- `sudo usermod -aG sudo analyst`
- `groups analyst`

![Group Assignment](../Screenshots/Week2/Week2_6_uptime.png)

---

## 9. Confidential File Protection

A confidential file was created and protected:

- `touch secret.txt`
- `sudo chown analyst:analyst secret.txt`
- `sudo chmod 600 secret.txt`

This ensures only the analyst can read or modify the file.

![Secret File Restricted](../Screenshots/Week2/Week2_7_users_created.png)

File permissions were confirmed:

![Secret Permissions](../Screenshots/Week2/Week2_8_user_list.png)

---

## 10. Unauthorized Access Attempt

The auditor user attempted access:

- `su auditor`
- `cat secret.txt`

The operating system correctly denied access.

![Unauthorized Attempt](../Screenshots/Week2/Week2_9_sudo_group.png)

![Permission Denied](../Screenshots/Week2/Week2_10_file_restriction.png)

---

## 11. Authorized Access Confirmation

The analyst account successfully accessed the protected file:

- `su analyst`
- `cat secret.txt`

![Authorized Access](../Screenshots/Week2/Week2_11_permission_denied.png)

---

## 12. Security Evaluation Summary

| Security Area | Result |
|--------------|--------|
| SSH Service | Secure & Active |
| Network Configuration | Verified & Stable |
| File Permissions | Enforced |
| File Ownership | Correctly Assigned |
| User Privilege Separation | Successfully Implemented |
| Unauthorized Access | Blocked |
| Authorized Access | Permitted |

---

## 13. Reflection

This week demonstrated how operating system security is enforced through concrete technical controls rather than theoretical policy.  
By combining SSH verification, strict file permissions, ownership enforcement, and user privilege separation, the system now operates with a strong security posture suitable for professional server environments.

This foundation enables the implementation of firewall rules, intrusion detection, and performance monitoring in later weeks.

---

### 🔗 Navigation

[Back to Index](index.md) | [Week 1](Week1.md) | **Week 2** | [Week 3](Week3.md) | [Week 4](Week4.md) | [Week 5](Week5.md) | [Week 6](Week6.md) | [Week 7](Week7.md)
