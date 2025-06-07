# 🛠️ Shell Scripting Mini Project: Error Handling with AWS S3 Buckets

This project demonstrates how to implement **error handling** in a Bash script by automating the creation of AWS S3 buckets and gracefully handling cases where buckets already exist.

---

## 📌 Project Objective

To create S3 buckets for different departments in a company and ensure that:
- Existing buckets are not recreated.
- Errors are caught and handled gracefully.
- Users receive informative feedback.

---

## 🧾 Script Details

### Script: `create_s3_buckets.sh`

#### ✅ What it does:
- Defines an array of departments.
- Iterates through the list to generate S3 bucket names.
- Checks if a bucket already exists using AWS CLI.
- Creates the bucket if it does not exist.
- Displays clear success or failure messages.

---

## 🖥️ Requirements

- AWS CLI installed and configured:
  ```bash
  aws configure
  ```
- IAM user or role with permissions to:
  - `s3:ListBucket`
  - `s3:CreateBucket`
- Bash shell (Linux, macOS, or WSL on Windows)

---

## 🚀 Usage

1. Clone or download the project.
2. Make the script executable:

   ```bash
   chmod +x create_s3_buckets.sh
   ```

3. Run the script:

   ```bash
   ./create_s3_buckets.sh
   ```

4. Example output:
   ```
   Processing bucket: datawise-marketing-data-bucket
   ✅ S3 bucket 'datawise-marketing-data-bucket' created successfully.
   ...
   ❗ S3 bucket 'datawise-sales-data-bucket' already exists.
   ```

---
<img width="700" alt="Image" src="https://github.com/user-attachments/assets/ed705439-1c31-45c7-b06d-e08323526d25" />

## ⚙️ Technologies Used

- Bash Scripting 🐚
- AWS CLI ☁️
- Linux Terminal 🖥️

---

## 📁 Files Included

| File Name              | Description                          |
|------------------------|--------------------------------------|
| `create_s3_buckets.sh` | Main script with error handling logic |
| `README.md`            | This documentation file              |

---

## 📚 Learning Outcomes

- Learn how to use arrays and loops in Bash.
- Understand how to interact with AWS CLI in a script.
- Practice implementing conditional logic for error handling.

---

