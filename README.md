
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

```text
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
