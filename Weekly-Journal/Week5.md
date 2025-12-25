#  Week 5 – User Management & Access Control

---

## 1. Introduction

Week 5 focused on implementing operating system access control using Linux user accounts, groups, and permission enforcement.  
These mechanisms represent the core security model of Unix-like systems and provide practical examples of authentication (who the user is), authorisation (what they are allowed to do), and access control (how permissions are enforced on resources).

This week’s work demonstrates a complete administrative workflow: establishing a baseline, applying changes, validating authorised access, proving unauthorised denial, and restoring the system state through clean-up.

---

## 2. Objectives for This Week

The objectives of Week 5 were:

- Inspect existing users and groups to create a baseline  
- Create a new user account for controlled permission testing  
- Create a dedicated security group for group-based access control  
- Assign users to groups to model role-based access  
- Create a protected directory with least-privilege permissions  
- Validate authorised access using an in-group user  
- Validate access denial using an out-of-group user  
- Remove test users/groups and clean up created resources  

---

## 3. Baseline User Inspection

Before introducing new test accounts, existing users were listed to document the system’s current authentication environment and establish a baseline state.

### Screenshot: Existing Users

![Existing Users](/Screenshots/Week5/1_week5_existing_users.png)

This baseline supports traceability by showing what accounts existed before changes were made.

---

## 4. Baseline Group Inspection

Groups were inspected to document how the system organises access control roles and administrative permissions.

### Screenshot: Existing Groups

![Existing Groups](/Screenshots/Week5/2_week5_existing_groups.png)

This establishes the pre-change group structure before new access control roles were introduced.

---

## 5. User Creation

A new user account was created for access testing. This user represents a legitimate account that can be granted permissions through group membership.

### Screenshot: User Created

![User Created](/Screenshots/Week5/3_week5_user_created.png)

---

## 6. Group Creation

A dedicated group was created to represent an access control role. This allows permissions to be assigned at the group level, supporting scalable administration.

### Screenshot: Group Created

![Group Created](/Screenshots/Week5/4_week5_group_created.png)

---

## 7. Adding the User to the Security Group

The test user was added to the security group, enabling group-based authorisation.  
This step demonstrates how Linux groups are used to assign access rights without changing ownership per-user.

### Screenshot: User Added to Group

![User Added to Group](/Screenshots/Week5/5_week5_user_added_to_group.png)

---

## 8. Verification of User Group Membership

The user’s identity and group memberships were verified to ensure the authorisation change took effect correctly.

### Screenshot: Group Membership Verified

![Group Verify](/Screenshots/Week5/6_week5_user_group_verify.png)

This confirms that the user is correctly associated with the intended group role.

---

## 9. Secure Directory Creation and Permission Enforcement

A protected directory was created and configured so that:

- `root` retains administrative ownership  
- the directory group controls authorised access  
- permissions allow access only to owner and group (770)  

This enforces least privilege by blocking all other users.

### Screenshot: Secure Directory Configuration

![Secure Directory](/Screenshots/Week5/7_week5_secure_directory.png)

This configuration implements a practical access control boundary on the filesystem.

---

## 10. Authorised Access Test (Allowed)

The group member user was tested to confirm authorised access works as intended.  
Successful access and file creation verifies the permission model is correctly applied.

### Screenshot: Secure Access Success

![Access Success](/Screenshots/Week5/8_week5_secure_access_success.png)

This demonstrates that access is granted only to authorised users under the defined policy.

---

## 11. Unauthorised Access Test (Denied)

An additional user (not a member of the security group) attempted access to the protected directory.  
The expected result is permission denial, demonstrating enforcement of access control and prevention of unauthorised operations.

### Screenshot: Permission Denied

![Permission Denied](/Screenshots/Week5/9_week5_permission_denied.png)

This is critical evidence that the security boundary is effective.

---

## 12. Cleanup and System Restoration

All test accounts, groups, and created directories were removed to restore the system to a clean baseline state.  
This demonstrates professional administration practices and prevents test artefacts remaining on the server.

### Screenshot: Cleanup Completed

![Cleanup](/Screenshots/Week5/10_week5_cleanup.png)

---

## 13. Security Summary

| Control Implemented | Evidence | Outcome |
|--------------------|----------|---------|
| Baseline user listing | Screenshot 1 | Documented authentication environment |
| Baseline group listing | Screenshot 2 | Documented authorisation roles |
| User creation | Screenshot 3 | Test identity created |
| Group creation | Screenshot 4 | Role-based access group created |
| Group assignment | Screenshot 5 | Authorisation applied through membership |
| Membership verification | Screenshot 6 | Access role confirmed |
| Protected directory | Screenshot 7 | Permission boundary created |
| Authorised access test | Screenshot 8 | Access permitted for authorised user |
| Unauthorised access test | Screenshot 9 | Access blocked for unauthorised user |
| Cleanup | Screenshot 10 | System returned to baseline |

---

## 14. Key Learning Outcomes

- Understanding how Linux uses users and groups to control access  
- Implementation of group-based authorisation in a scalable way  
- Correct use of ownership (`chown`) and permission bits (`chmod`)  
- Practical validation of both access grant and access denial  
- Application of least privilege and secure administration workflow  

---

## 15. Reflection

Week 5 demonstrated that operating system security is largely enforced through identity and permissions.  
By creating a role-based access group, restricting a directory, and validating behaviour with authorised and unauthorised users, the system’s access control model was tested in a controlled and evidence-based way.

This workflow mirrors professional administration practice by combining baseline auditing, controlled configuration changes, validation testing, and full cleanup to preserve system integrity.

---

### 🔗 Navigation

[Back to Index](index.md) | [Week 1](Week1.md) | [Week 2](Week2.md) | [Week 3](Week3.md) | [Week 4](Week4.md) | **Week 5** | [Week 6](Week6.md) | [Week 7](Week7.md)
