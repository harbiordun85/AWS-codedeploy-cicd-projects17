# 🚀 my-project17-cicd-pipeline

## End-to-End CI/CD Pipeline with GitHub, S3, CodeBuild, CodeDeploy & CodePipeline

This project demonstrates how to build a fully automated CI/CD pipeline on AWS using GitHub as the source, **Amazon S3 as the artifact store**, 
and AWS native services for building, deploying, and orchestrating the workflow. It also integrates **manual approval via SNS** for a realistic enterprise-style deployment.

---

## 🛠️ Technologies & Services Used

- **GitHub** – Source control
- **Amazon S3** – Artifact storage
- **AWS CodeBuild** – Build and test automation
- **AWS CodeDeploy** – Deployment to EC2
- **AWS CodePipeline** – CI/CD orchestration
- **AWS SNS** – Notification and manual approval
- **IAM** – Custom roles and permissions for secure access

---

## 📦 Project Architecture
## GitHub (Source) ↓ CodePipeline (Trigger) ↓ CodeBuild (Build + Package) ↓ S3 (Stores build artifact) ↓ SNS (Approval Notification) ↓ CodeDeploy (Deployment to EC2)


---

## 📌 Key Features

- ✅ **Automated Build & Deploy Pipeline**
- ✅ **S3-Based Artifact Storage**
- ✅ **EC2 Deployment via CodeDeploy**
- ✅ **Manual Approval Step via SNS**
- ✅ **IAM Role-based Security**
- ✅ **Modular and Production-Ready Setup**

---

## 🔨 Implementation Steps

### 1. **Set Up GitHub Repository**
- Pushed application code, `buildspec.yml`, and `appspec.yml` to GitHub.

### 2. **Create S3 Bucket for Artifacts**
- Bucket name: `s3-application-proj17-2024`
- Configured IAM policies for CodeBuild and CodePipeline to read/write artifacts.

### 3. **Provision IAM Roles**
- Created roles for:
  - CodeBuild (access to S3, CodeDeploy)
  - CodePipeline (access to GitHub, S3, SNS)
  - EC2 (for CodeDeploy agent communication)

### 4. **Configure CodeBuild**
- Connected to GitHub repository.
- Used `buildspec.yml` to:
  - Install dependencies
  - Package code
  - Upload artifact ZIP to S3

### 5. **Set Up CodeDeploy**
- Created a deployment group for EC2 using tags.
- Defined lifecycle hooks in `appspec.yml`.

### 6. **Configure CodePipeline**
- **Source**: GitHub
- **Build**: CodeBuild
- **Approval**: Manual approval via SNS
- **Deploy**: CodeDeploy

### 7. **SNS Approval Integration**
- Created an SNS topic
- Subscribed a senior engineer’s email for approval.
- Pipeline pauses for approval before deploying to EC2.

---

## ✅ Result

- CI/CD pipeline fully automates from source to deployment.
- Artifacts stored and managed efficiently in Amazon S3.
- Code is built, approved, and deployed with minimal manual effort.
- Approval adds an extra layer of control for production-like environments.

---

## 📸 Screenshots (Optional)
> Add CodePipeline diagram, SNS email approval screenshot, or S3 artifact view here.

## 💬 Author

**Abiodun — DevOps Engineer**

> Feel free to connect with me on https://www.linkedin.com/in/abiodun-adejumo-devops/



