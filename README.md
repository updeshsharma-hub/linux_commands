# 🐧 Linux Command Cyber Dashboard

**Live Demo:** [View the Dashboard Here](http://updesh-web.s3-website.ap-south-1.amazonaws.com) *(Note: Currently hosted via HTTP on S3)*

## 📖 Overview
The **Linux Command Cyber Dashboard** is a fast, static web application designed to serve as a quick-reference guide for common Linux commands, categorized by difficulty and type. 

Beyond the frontend, this project serves as a practical implementation of **Cloud Hosting** and **Continuous Deployment (CI/CD)**. It automatically deploys to Amazon Web Services (AWS) whenever new code is pushed to the repository.

## 🏗️ Architecture & Technologies Used
* **Frontend:** HTML, CSS, JavaScript
* **Cloud Provider:** Amazon Web Services (AWS)
* **Hosting:** AWS S3 (Configured for Static Website Hosting)
* **CI/CD:** GitHub Actions
* **Security & Access:** AWS IAM (Dedicated, least-privilege user for automated deployments)

## ⚙️ How the CI/CD Pipeline Works
This project utilizes a GitHub Actions workflow (`deploy.yml`) to eliminate manual uploads and ensure the live site is always up to date.

1. **Trigger:** A developer pushes code changes to the `main` branch.
2. **Checkout:** GitHub Actions spins up an Ubuntu runner and checks out the repository.
3. **Authentication:** The workflow securely authenticates with AWS using IAM credentials stored in GitHub Secrets (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`).
4. **Deploy:** The `aws s3 sync` command runs, pushing the updated static files to the S3 bucket (`updesh-web`) and deleting any removed files, making the updates instantly live.

## 🚀 Future Enhancements
* **Implement HTTPS:** Put an AWS CloudFront distribution in front of the S3 bucket to provide a secure SSL/TLS connection.
* **Infrastructure as Code (IaC):** Migrate the manual AWS console setup (S3 bucket, IAM user, and policies) to Terraform for reproducible infrastructure.
* **Custom Domain:** Route traffic through AWS Route 53 to attach a custom domain name.

## 👨‍💻 Author
**Updesh Sharma** - [GitHub Profile](https://github.com/updeshsharma-hub)
