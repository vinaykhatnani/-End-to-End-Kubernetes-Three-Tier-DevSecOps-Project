# 🚀 End-to-End Kubernetes Three-Tier DevSecOps Project

## 📌 Project Overview

This project demonstrates a **complete DevSecOps pipeline** for deploying a **three-tier application** using modern DevOps tools and cloud technologies. It covers everything from infrastructure provisioning to CI/CD, security scanning, monitoring, and GitOps deployment.

The application consists of:

* **Frontend** → React.js
* **Backend** → Node.js
* **Database** → MongoDB

The entire system is deployed on **AWS EKS (Elastic Kubernetes Service)** with a fully automated pipeline.

---

## 🧠 Architecture

```
GitHub → Jenkins → Docker → AWS ECR → Kubernetes (EKS)
                                      ↓
                              ArgoCD (GitOps)
                                      ↓
                        Prometheus + Grafana (Monitoring)
```

---

## ⚙️ Tech Stack

### ☁️ Cloud & Infrastructure

* AWS (EC2, EKS, ECR, IAM, S3, DynamoDB)
* Terraform (Infrastructure as Code)

### ⚙️ DevOps Tools

* Jenkins (CI/CD)
* Docker (Containerization)
* Kubernetes (Container Orchestration)
* ArgoCD (GitOps Deployment)

### 🔐 DevSecOps Tools

* SonarQube (Code Quality)
* Trivy (Container Security Scanning)
* OWASP Dependency Check

### 📊 Monitoring

* Prometheus
* Grafana

---

## 📁 Project Structure

```
.
├── Application-Code/        # Frontend & Backend source code
├── Jenkins-Pipeline-Code/   # Jenkins pipeline scripts
├── Kubernetes-Manifests-file/ # K8s deployment & service YAMLs
├── Jenkins-Server-TF/       # Terraform files for Jenkins setup
└── README.md
```

---

## 🔥 Features

* ✅ Automated Infrastructure Provisioning using Terraform
* ✅ CI/CD Pipeline using Jenkins
* ✅ Dockerized Application
* ✅ Secure Image Scanning (Trivy)
* ✅ Code Quality Analysis (SonarQube)
* ✅ Kubernetes Deployment on AWS EKS
* ✅ GitOps Continuous Deployment using ArgoCD
* ✅ Real-time Monitoring with Prometheus & Grafana

---

## 🛠️ Step-by-Step Setup

### 1️⃣ Clone Repository

```bash
git clone <your-repo-url>
cd End-to-End-Kubernetes-Three-Tier-DevSecOps-Project
```

---

### 2️⃣ Setup AWS CLI

```bash
aws configure
```

---

### 3️⃣ Provision Infrastructure (Terraform)

```bash
cd Jenkins-Server-TF
terraform init
terraform plan
terraform apply
```

This will create:

* Jenkins EC2 Server
* Required networking & backend resources

---

### 4️⃣ Setup Jenkins

* Access Jenkins: `http://<EC2-Public-IP>:8080`

* Install required plugins:

  * Docker
  * Kubernetes
  * Git
  * Pipeline

* Configure credentials:

  * AWS Credentials
  * GitHub Token
  * Docker Hub / ECR

---

### 5️⃣ Dockerize Application

```bash
cd Application-Code
docker build -t frontend .
docker build -t backend .
```

---

### 6️⃣ Push Images to AWS ECR

```bash
aws ecr create-repository --repository-name frontend
aws ecr create-repository --repository-name backend
```

Tag & push images to ECR.

---

### 7️⃣ Create EKS Cluster

```bash
eksctl create cluster --name my-cluster
kubectl get nodes
```

---

### 8️⃣ Deploy Application to Kubernetes

```bash
cd Kubernetes-Manifests-file
kubectl apply -f .
```

---

### 9️⃣ Setup CI/CD Pipeline (Jenkins)

Pipeline stages:

* Code Checkout
* Build Docker Images
* SonarQube Analysis
* Trivy Security Scan
* Push to ECR
* Deploy to Kubernetes

---

### 🔟 Setup ArgoCD (GitOps)

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Access ArgoCD UI and connect your GitHub repo for auto-deployment.

---

### 1️⃣1️⃣ Setup Monitoring

```bash
helm install prometheus prometheus-community/kube-prometheus-stack
```

* Access Grafana dashboards
* Monitor application performance

---

## 🔐 Security Implementation

* ✔️ Static Code Analysis using SonarQube
* ✔️ Container Image Scanning using Trivy
* ✔️ Dependency Vulnerability Check (OWASP)

---

## 📊 Monitoring & Observability

* **Prometheus** → Collects metrics
* **Grafana** → Visualizes dashboards
* Tracks:

  * CPU Usage
  * Memory Usage
  * Pod Health

---

## 🚀 Final Outcome

* Fully automated DevSecOps pipeline
* Secure, scalable Kubernetes deployment
* Continuous monitoring & GitOps-based delivery

---

## 🎯 Learning Outcomes

By completing this project, you will understand:

* End-to-end DevOps workflow
* Infrastructure as Code (Terraform)
* CI/CD pipeline design
* Kubernetes deployment strategies
* DevSecOps practices
* Monitoring & observability

---

## 🤝 Contributing

Feel free to fork this repository and enhance the project. Contributions are welcome!

---

## 📬 Contact

For any queries or collaboration, feel free to connect.

---

## ⭐ If you found this helpful

Give this repo a ⭐ and share with others!

---
