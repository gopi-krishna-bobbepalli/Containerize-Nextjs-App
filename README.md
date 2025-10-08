# 🚀 Containerize and Deploy a Next.js Application using Docker, GitHub Actions, and Minikube

## 📘 Project Overview

This project demonstrates how to **containerize a Next.js application** using Docker,  
automate the **build and push of the image** to **GitHub Container Registry (GHCR)** via GitHub Actions,  
and finally **deploy the containerized application to Kubernetes (Minikube)**.

---

## 🧱 1. Setup Instructions

### 🧩 Prerequisites
Ensure the following are installed on your system:
- **Node.js (v18 or later)**
- **Docker**
- **Git**
- **Minikube**
- **kubectl**
- **GitHub account (for GHCR access)**

### 🪄 Clone the Repository
```bash
git clone https://github.com/gopi-krishna-bobbepalli/Containerize-Nextjs-App.git
cd Containerize-Nextjs-App
```
## 💻 2. Local Run Commands

### 🏗️ Install Dependencies
```bash
npm install
```
### ▶️ Run the Application Locally
```bash
npm run dev
```
Access  app at: http://localhost:3000

## 🐳 3. Docker Containerization
### 🧾 Build Docker Image
```bash
docker build -t nextjs-docker-demo .
```
### ▶️ Run Docker Container
```bash
docker run -p 3000:3000 nextjs-docker-demo
```
app will now be available at:👉 http://localhost:3000

## ⚙️ 4. CI/CD with GitHub Actions & GHCR
### 🔁 Workflow Automation
A GitHub Actions workflow (.github/workflows/docker-build.yml) automates:
- Building the Docker image on each push to the main branch
- Pushing the image to GitHub Container Registry (GHCR)

### 🧩 Example Image Name
```bash
ghcr.io/gopi-krishna-bobbepalli/containerize-nextjs-app:latest
```
## ☸️ 5. Deployment Steps for Minikube
### 🧭 Start Minikube
```bash
minikube start
```
Verify:
```bash
minikube status
```
### 📦 Apply Kubernetes Manifests
All manifests are in the k8s/ folder.
#### 🧱 Deployment
```bash
kubectl apply -f k8s/deployment.yaml
```
#### 🌐 Service
```bash
kubectl apply -f k8s/service.yaml
```
Verify everything:
```bash
kubectl get pods
kubectl get svc
```
### 🌍 6. Access the Deployed Application
Run:
```bash
minikube service nextjs-service
```

