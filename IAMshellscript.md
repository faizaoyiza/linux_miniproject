# AWS IAM Management Automation Script

## Introduction

This project provides a shell script to automate AWS Identity and Access Management (IAM) resource management. It creates multiple IAM users, a dedicated admin group, and attaches an administrative policy to that group. Automating these tasks helps streamline onboarding of new team members and simplifies permission management.

---

## Objectives

- Define an array of IAM user names.
- Create IAM users iteratively from the array.
- Create an IAM group named `"admin"`.
- Attach the `AdministratorAccess` AWS-managed policy to the `"admin"` group.

---

## Prerequisites

- AWS CLI installed and configured (`aws configure`)
- AWS account with permissions to manage IAM resources
- Bash shell environment

---

## Implementation Details

### Thought Process

- Use a Bash array to store user names for easy iteration.
- Write functions for creating users and groups, and attaching policies.
- Incorporate checks to avoid errors if resources already exist.
- Use AWS CLI commands:
  - `aws iam create-user`
  - `aws iam create-group`
  - `aws iam attach-group-policy`
  - `aws iam get-user` and `aws iam get-group` for existence checks.

---
<img width="950" height="463" alt="Image" src="https://github.com/user-attachments/assets/c25ba762-80fd-4927-918f-a3d405a57a90" />




<img width="948" height="512" alt="Image" src="https://github.com/user-attachments/assets/c9007cee-2fd6-4588-b46d-ea0fe786024b" />

## Final Script: `aws-iam-manager.sh`

```bash
#!/bin/bash

# Array of IAM user names
iam_users=("alice" "bob" "charlie" "diana" "eve")

# Function to create IAM users
create_iam_users() {
  for user in "${iam_users[@]}"; do
    echo "Creating IAM user: $user"
    # Check if user already exists
    if aws iam get-user --user-name "$user" 2>/dev/null; then
      echo "User $user already exists. Skipping creation."
    else
      aws iam create-user --user-name "$user"
      if [ $? -eq 0 ]; then
        echo "Successfully created user: $user"
      else
        echo "Failed to create user: $user"
      fi
    fi
  done
}

# Function to create IAM group and attach policy
create_admin_group() {
  local group_name="admin"
  echo "Creating IAM group: $group_name"
  
  # Check if group exists
  if aws iam get-group --group-name "$group_name" 2>/dev/null; then
    echo "Group $group_name already exists. Skipping creation."
  else
    aws iam create-group --group-name "$group_name"
    if [ $? -eq 0 ]; then
      echo "Successfully created group: $group_name"
    else
      echo "Failed to create group: $group_name"
      return 1
    fi
  fi

  # Attach AdministratorAccess policy
  local policy_arn="arn:aws:iam::aws:policy/AdministratorAccess"
  echo "Attaching policy to group: $policy_arn"
  aws iam attach-group-policy --group-name "$group_name" --policy-arn "$policy_arn"
  if [ $? -eq 0 ]; then
    echo "Policy attached successfully."
  else
    echo "Failed to attach policy."
  fi
}

# Main execution
echo "Starting IAM management script..."

create_iam_users
create_admin_group

echo "IAM setup completed."

