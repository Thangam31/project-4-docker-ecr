# Project 4: Secure Microservice Containerization & ECR Deployment

## 📌 Overview
Containerized a lightweight monitoring microservice using Docker with Zero-Trust security and deployed to AWS ECR.

## 🛠️ Tech Stack
- OS: Ubuntu 22.04 LTS
- Container Engine: Docker v29.1.3
- Base Image: Alpine Linux 3.19
- Cloud Provider: AWS ECR (ap-south-1)

## 🔐 Security Best Practices
1. Minimal Footprint (Alpine Linux ~5MB)
2. Non-Root Execution (appuser)
3. Automated Scanning (scanOnPush=true)

## 🚀 Execution Steps
```bash
docker build -t appedge-monitor:v1 .
aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 891447917545.dkr.ecr.ap-south-1.amazonaws.com
docker tag appedge-monitor:v1 891447917545.dkr.ecr.ap-south-1.amazonaws.com/appedge-monitor:v1
docker push 891447917545.dkr.ecr.ap-south-1.amazonaws.com/appedge-monitor:v1
```

## ✅ Result
- ECR URI: 891447917545.dkr.ecr.ap-south-1.amazonaws.com/appedge-monitor:v1

