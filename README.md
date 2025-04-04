
# 📦 AWS Lambda + S3 Trigger with Terraform

This project provisions an **AWS Lambda function** using **Terraform** to automatically organize uploaded files in an **S3 bucket**. The Lambda function is triggered whenever a new file is uploaded to a specific path (`incoming/`). It moves files into folders organized by `Year/Month/Date`.

---

## 🚀 Project Overview

- ✅ **Infrastructure as Code** using Terraform
- 🐍 **Python** used for Lambda function logic
- 🪣 **S3 Trigger**: Fires Lambda on new uploads to `incoming/` path
- 🧠 Lambda parses filenames and moves them into `incoming/<year>/<month>/<date>/filename.txt`
- 🔒 IAM policies and roles are created automatically

---

## 🧱 Architecture

---
               ┌─────────────┐
               │   User      │
               └─────┬───────┘
                     │ uploads file to S3
                     ▼
         ┌────────────────────────────┐
         │  S3 Bucket: inbound-bucket │
         │     /incoming/             │
         └────────────┬───────────────┘
                      │ triggers
                      ▼
               ┌──────────────┐
               │  Lambda      │
               │  Function    │
               └────┬─────────┘
                    │ moves files to
                    ▼
   incoming/<year>/<month>/<day>/filename.txt

---

## 📁 Directory Structure
---text
.
├── lambda.tf                 # All Terraform resources
├── variables.tf              # Input variables
├── outputs.tf                # Terraform outputs
├── versions.tf              # Terraform version constraint
├── lambda_functions/
│   └── main.py               # Python Lambda logic
├── lambda_code.zip           # Auto-generated ZIP from archive_file
└── README.md


