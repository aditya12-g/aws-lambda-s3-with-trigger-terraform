# AWS Lambda + S3 Trigger using Terraform

This project provisions an AWS Lambda function using Terraform that listens for new file uploads to an S3 bucket path (`incoming/`). When a file is uploaded, the Lambda function organizes it into folders based on the file name's date (`Year/Month/Date/filename.txt`).

---

## ✅ Features

- Infrastructure as Code using Terraform
- Python Lambda function triggered by S3
- Automatically moves files to structured folders
- IAM roles and permissions managed with Terraform

---

## 🧠 How It Works

1. Upload a file to `s3://inbound-bucket-custom/incoming/`
2. Lambda is triggered via S3 notification
3. Python code extracts `year/month/date` from filename
4. File is moved to `incoming/<year>/<month>/<date>/filename.txt`
5. Original file is deleted

---

## 📁 Project Structure

- `lambda.tf` – Terraform configuration for Lambda, IAM, S3 triggers
- `variables.tf` – (Optional) Define Terraform variables
- `lambda_functions/main.py` – Python Lambda function logic
- `README.md` – This file

---

## 🚀 Deployment Steps

```bash
# Clone the repository
git clone https://github.com/aditya12-g/aws-lambda-s3-with-trigger-terraform.git
cd aws-lambda-s3-with-trigger-terraform

# Initialize Terraform
terraform init

# Apply the infrastructure
terraform apply







