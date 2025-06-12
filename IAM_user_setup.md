# IAM User and Group Setup for Zappy e-Bank

## Overview

This document outlines the setup of IAM users and groups for Zappy e-Bank's AWS infrastructure, focusing on role-based access control. It includes creating policies, user groups, and users for backend developers and data analysts, using the principle of least privilege.

---

## Roles and Access Requirements

### Backend Developer: John
- Requires access to **EC2** to deploy and manage code.

### Data Analyst: Mary
- Requires access to **S3** for data storage and analysis.

---

## Step-by-Step Guide

### 1. Create IAM Policies

#### Developer Policy
- Go to **IAM Console > Policies > Create Policy**.
- Service: **EC2**
- Actions: **All EC2 actions**
- Resources: **All**
- Name: `developers`

#### Analyst Policy
- Service: **S3**
- Actions: **All S3 actions**
- Resources: **All**
- Name: `analysts`

### 2. Create IAM Groups

#### Development-Team Group
- Go to **IAM Console > User Groups > Create Group**
- Name: `Development-Team`
- Attach Policy: `developers`

#### Analyst-Team Group
- Name: `Analyst-Team`
- Attach Policy: `analysts`
<img width="950" alt="Image" src="https://github.com/user-attachments/assets/be380674-40f5-476b-83c8-8deeb5346046" />

### 3. Create IAM Users

#### John (Backend Developer)
- Go to **IAM Console > Users > Create User**
- Username: `John`
- Console Access: Enabled
- Add to Group: `Development-Team`

#### Mary (Data Analyst)
- Username: `Mary`
- Console Access: Enabled
- Add to Group: `Analyst-Team`

---
<img width="950" alt="Image" src="https://github.com/user-attachments/assets/9872628f-3f37-4eeb-814f-858e33b43824" />
## Testing and Validation

### John (EC2 Access)
- Login with John's credentials.
- Access EC2 dashboard.
- Launch or manage EC2 instances.

### Mary (S3 Access)
- Login with Mary's credentials.
- Access S3 dashboard.
- Create or manage S3 buckets.

Ensure each user **only** accesses resources relevant to their role.

---

## Enable Multi-Factor Authentication (MFA)

### Why MFA?
MFA provides an extra layer of security by requiring a time-based one-time password (TOTP) in addition to username and password.

### Setup MFA for John
1. Go to **IAM Console > Users > John**
2. Click **Security credentials > Assign MFA device**
3. Choose **Authenticator app**
4. Scan QR code using **Google Authenticator** or **Microsoft Authenticator**
5. Enter two consecutive TOTP codes to verify

---
<img width="928" alt="Image" src="https://github.com/user-attachments/assets/e34e7ea8-0052-4898-aec3-33b980e498b5" />
## Project Reflection

### Role of IAM in AWS
IAM enables secure management of AWS services by controlling who can access which resources.

### IAM Users vs Groups
- **Users**: Individual identities with their own credentials.
- **Groups**: Collections of users with shared permissions.

### Creating IAM Policies
- Define access using JSON or visual editor.
- Attach to groups or users based on roles.

### Principle of Least Privilege
Users are granted the **minimum** permissions required to perform their job—reducing risk of misuse or compromise.

### Scenario Recap
- **John**: IAM user in `Development-Team` with EC2 access only.
- **Mary**: IAM user in `Analyst-Team` with S3 access only.
- Both setups follow the principle of least privilege.

---

## Summary

This setup ensures efficient user management, scalability, and secure access control. As the team expands, new users can be added to appropriate groups without recreating policies.
