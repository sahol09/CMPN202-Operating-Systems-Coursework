#  Week 4 – Network Services, SSH & Firewall Configuration

---

## 1. Introduction

Week 4 focused on implementing network-level security controls to protect the Ubuntu Server from unauthorised access.  
Unlike earlier weeks that focused on observation and baselining, this week applied active security mechanisms to reduce the system’s attack surface and enforce least-privilege access at the network boundary.

All administration was performed remotely where possible in line with coursework expectations, and all changes were validated with pre and post configuration checks.

---

## 2. Objectives for This Week

The objectives of Week 4 were:

- Inspect active network services and exposed ports  
- Identify running services that contribute to the attack surface  
- Confirm filesystem and system stability before applying security changes  
- Configure and enable UFW firewall rules using least privilege principles  
- Restrict inbound traffic to required services only (SSH)  
- Verify enforcement using both UFW and iptables  
- Ensure secure remote access is maintained and documented  

---

## 3. Network Services & Exposure Baseline

Before applying any firewall policy, active listening ports were inspected to understand which services were exposed.

### Screenshot: Active Network Ports (Pre-Hardening)

![Active Ports](../Screenshots/Week4/1_week4_active_ports.png)

This baseline provides evidence of the system’s initial network exposure and supports later comparison after security enforcement.

---

## 4. Service Enumeration (Attack Surface Review)

Running system services were reviewed to identify what the server is actively providing at runtime and which services may potentially expose network endpoints.

### Screenshot: Running Services

![Running Services](../Screenshots/Week4/2_week4_running_services.png)

This step supports secure hardening by making service activity visible and auditable.

---

## 5. Filesystem & Disk Validation (Pre-Change Safety Check)

Before applying security controls, disk usage, mounted filesystems, and block devices were inspected to confirm system stability and ensure changes were performed on a healthy environment.

### Screenshot: Filesystem Status

![Filesystem Status](../Screenshots/Week4/3_week4_filesystem_status.png)

This provides administrative assurance that the system is stable prior to firewall enforcement.

---

## 6. Firewall Installation (UFW)

UFW (Uncomplicated Firewall) was installed as the host-based firewall solution to manage inbound and outbound rules in a structured way.

### Screenshot: UFW Installed

![UFW Install](../Screenshots/Week4/4_week4_ufw_install.png)

---

## 7. Firewall Policy Configuration (Least Privilege)

Firewall defaults were configured to follow a secure baseline:

- Deny all incoming traffic by default  
- Allow outgoing traffic by default  

This approach ensures services are not exposed unless explicitly approved.

### Screenshot: Default Firewall Policies

![Firewall Policies](../Screenshots/Week4/5_week4_ufw_policies.png)

---

## 8. SSH Allow Rule (Maintaining Secure Administration)

To preserve secure remote administration, SSH was explicitly allowed through the firewall.

### Screenshot: SSH Allowed

![Allow SSH](../Screenshots/Week4/6_week4_allow_ssh.png)

This ensures remote access is available while keeping all other inbound traffic restricted.

---

## 9. Firewall Activation

The firewall was enabled to enforce the configured rules at runtime.

### Screenshot: Firewall Enabled

![UFW Enabled](../Screenshots/Week4/7_week4_ufw_enabled.png)

---

## 10. Firewall Verification (UFW Status)

Firewall status was checked using verbose output to confirm rules are active and correctly applied.

### Screenshot: UFW Status (Verbose)

![UFW Status](../Screenshots/Week4/8_week4_ufw_status.png)

This demonstrates configuration accuracy and confirms the security policy is enforced.

---

## 11. Post-Hardening Validation (Attack Surface Reduction)

After firewall activation, active listening ports were re-checked to confirm the system’s network exposure aligns with the new policy.

### Screenshot: Active Ports (Post-Hardening)

![Post Firewall Ports](../Screenshots/Week4/9_week4_post_firewall_ports.png)

This provides direct evidence that hardening reduced exposed services and supports the security objective of attack surface minimisation.

---

## 12. Kernel-Level Verification (iptables)

iptables rules were inspected to verify that UFW policies are enforced at the underlying packet-filtering layer.

### Screenshot: iptables Rules

![iptables Rules](../Screenshots/Week4/10_week4_iptables_rules.png)

This strengthens evidence by showing enforcement beyond the UFW interface.

---

## 13. Remote Administration Evidence

To demonstrate secure administration and confirm active sessions, the logged-in users were inspected.

### Screenshot: Remote Session Check

![Remote Session](../Screenshots/Week4/11_week4_remote_session.png)

This supports the coursework requirement for controlled and auditable administration activity.

---

## 14. SSH Continuity & Troubleshooting Evidence

During hardening, SSH continuity was tested to ensure firewall rules did not block remote access.  
A connectivity issue was detected (“connection refused”), which indicated that SSH access was being blocked or the service was not available.  
This was resolved by confirming the SSH service status and ensuring the firewall rule allowing port 22 (SSH) was applied correctly.

### Screenshot: SSH Service Status (Fix Verification)

![SSH Service Status](../Screenshots/Week4/12A_week4_ssh_service_status.png)

### Screenshot: Firewall Rule Fix (SSH Allowed)

![UFW SSH Fix](../Screenshots/Week4/12B_week4_ufw_ssh_fix.png)

### Screenshot: SSH Verified (Successful Connection)

![SSH Verified](../Screenshots/Week4/12_week4_ssh_verified.png)

This demonstrates secure configuration, troubleshooting competence, and validation of continued administrative access.

---

## 15. Security Summary

| Security Control | Result |
|------------------|--------|
| Service/Port Baseline | Documented before changes |
| Default Firewall Policy | Deny incoming, allow outgoing |
| SSH Access | Explicitly allowed and verified |
| Firewall Enforcement | Verified via UFW + iptables |
| Attack Surface | Reduced after hardening |
| Administration | Remote access confirmed and auditable |

---

## 16. Key Learning Outcomes

- Ability to identify exposed ports and services using network inspection tools  
- Understanding of attack surface reduction through firewall enforcement  
- Practical implementation of least privilege network access controls  
- Ability to verify firewall policies at both UFW and iptables levels  
- Improved troubleshooting capability when access was affected by hardening  

---

## 17. Reflection

Week 4 demonstrated that effective operating system security requires both configuration and verification.  
By analysing services, applying least-privilege firewall rules, and validating enforcement before and after changes, the server’s network exposure was reduced without losing secure administration capability.

This week reflects real-world system hardening practice, where security changes must be evidence-based, reversible, and validated to avoid accidental lockouts while improving protection.

---

### 🔗 Navigation

[Back to Index](index.md) | [Week 1](Week1.md) | [Week 2](Week2.md) | [Week 3](Week3.md) | **Week 4** | [Week 5](Week5.md) | [Week 6](Week6.md) | [Week 7](Week7.md)
