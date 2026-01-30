# Mini Project: Working with Functions in Bash (AWS Automation)

## 📌 Project Description

This mini-project is part of a larger DevOps automation task for **Data Wise Solutions**.  
The goal is to demonstrate how **functions in Bash scripting** can be used to build clean, modular, and reusable scripts that validate system requirements before automating AWS resources such as **EC2 instances** and **S3 buckets**.

At this stage, the focus is on:
- Input validation
- Environment checks
- AWS readiness verification

These checks are critical in real-world infrastructure automation to prevent failed deployments.

---

## 🎯 Project Objectives

The script performs the following tasks using functions:

- ✔️ Validate that the script receives exactly one argument  
- ✔️ Confirm that AWS CLI is installed  
- ✔️ Verify AWS authentication using environment variables  
- ✔️ Execute logic based on the specified environment  

---

## 🧠 Why Functions Were Used

Functions were introduced to:
- Improve readability and structure
- Avoid repetitive code
- Make the script easier to extend (EC2, S3 automation later)
- Follow DevOps best practices for maintainability

Each requirement is implemented as a **separate function**.

---

## 🛠️ Technologies Used

- Bash (Shell Scripting)
- AWS CLI
- Linux Environment

---

## 📂 Project Structure

```
project-root/
│
├── setup.sh
├── functions-mini-project.md
└── screenshots/
    ├── aws-cli-check.png
    ├── script-argument-check.png
    └── environment-output.png
```

---

## 🧾 Bash Script Implementation

```bash
#!/bin/bash

# -----------------------------
# Function: Check number of arguments
# -----------------------------
check_num_of_args() {
  if [ "$#" -ne 1 ]; then
    echo "Usage: $0 <environment>"
    echo "Example: $0 local | testing | production"
    exit 1
  fi
}

# -----------------------------
# Function: Check AWS CLI installation
# -----------------------------
check_aws_cli() {
  if ! command -v aws >/dev/null 2>&1; then
    echo "AWS CLI is not installed."
    exit 1
  fi
}

# -----------------------------
# Function: Check AWS authentication
# -----------------------------
check_aws_auth() {
  if [ -z "$AWS_ACCESS_KEY_ID" ] || [ -z "$AWS_SECRET_ACCESS_KEY" ]; then
    echo "AWS credentials not found."
    exit 1
  fi
}

# -----------------------------
# Script execution
# -----------------------------
check_num_of_args "$@"
check_aws_cli
check_aws_auth

ENVIRONMENT=$1

if [ "$ENVIRONMENT" = "local" ]; then
  echo "Running script for Local Environment..."
elif [ "$ENVIRONMENT" = "testing" ]; then
  echo "Running script for Testing Environment..."
elif [ "$ENVIRONMENT" = "production" ]; then
  echo "Running script for Production Environment..."
else
  echo "Invalid environment specified."
  exit 2
fi
```

---

<img width="439" height="239" alt="Image" src="https://github.com/user-attachments/assets/9f88e0e5-ffab-42ea-8fbb-a75863a9f058" />
<img width="917" height="520" alt="Image" src="https://github.com/user-attachments/assets/76341115-1c6b-44dc-97bc-3c834d64ee6e" />

---

## 📈 Next Phase of the Project

This script will be extended to include:
- EC2 instance provisioning functions
- S3 bucket creation
- Environment-specific infrastructure logic
- AWS automation best practices

---

## ✅ Key Takeaway

This mini-project demonstrates how Bash functions can be used to build **reliable, scalable, and production-ready automation scripts**, forming the foundation for real-world DevOps workflows.
