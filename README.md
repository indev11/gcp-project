# GCP DevOps Project – Docker Flask Application

## Overview
This project demonstrates the complete **DevOps lifecycle** for deploying a **Flask-based Docker application** on **Google Cloud Platform (GCP)** using **Kubernetes (GKE)** and **Cloud Build** for automation. The project follows a sprint-based approach to **CI/CD integration** and deployment.

## Tech Stack
- **Programming Language:** Python (Flask)
- **DevOps Tools:** Docker, Kubernetes (GKE), Cloud Build, Artifact Registry
- **Cloud Platform:** Google Cloud Platform (GCP)
- **Version Control:** GitHub

---

## Sprint Breakdown

### **Sprint 1: Project Initialization**
- Created a **GitHub repository** following best practices.
- Developed a **basic Flask application** and Dockerized it.
- Tested the Docker image locally.
- Pushed the project to **GitHub**.

### **Sprint 2: Setting Up GCP & Kubernetes**
- Created a **GCP account**.
- Set up **Google Kubernetes Engine (GKE)**.
- Configured a **GKE cluster** to host the application.

### **Sprint 3: Cloud Build & Automation**
- Explored **Cloud Build** fundamentals.
- Connected **Cloud Build to GitHub** for automated builds.
- Configured **Cloud Build triggers** to automate Docker image creation.

### **Sprint 4: CI/CD Workflow Implementation**
- Committed new changes to **GitHub**.
- Created a **pull request (PR)** and merged to the main branch.
- **Cloud Build** was triggered automatically.
- Docker image was stored in **GCP Artifact Registry**.

### **Sprint 5: Kubernetes Deployment**
- Created a **namespace** in the GKE cluster.
- Defined a **deployment.yaml** file for the application.
- Updated Cloud Build to automate Kubernetes deployment.
- Validated the deployment in GKE.

### **Sprint 6: Exposing the Application**
- Extended `gke.yaml` to include **service exposure**.
- Configured **Kubernetes Ingress** for public access.

### **Sprint 7: Production Deployment**
- Deployed the changes following the **DevOps lifecycle**.
- Ensured application scalability and availability.

---

## Setup & Deployment Guide

### **1. Clone the Repository**
```bash
 git clone https://github.com/your-username/gcp-devops-flask.git
 cd gcp-devops-flask
```

### **2. Build & Test Docker Image Locally**
```bash
 docker build -t flask-app .
 docker run -p 5000:5000 flask-app
```

### **3. Push to GitHub**
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

### **4. Configure GCP & Kubernetes**
- Create a **GKE cluster**.
- Enable **Cloud Build** and connect it to GitHub.
- Set up **Cloud Build triggers**.
- Deploy using `kubectl`:
```bash
kubectl apply -f deployment.yaml
```

### **5. Expose the Application**
- Configure **Ingress** to expose the app externally.
```bash
kubectl apply -f service.yaml
```

### **6. Validate the Deployment**
```bash
kubectl get pods -n your-namespace
kubectl get services -n your-namespace
```

---

## CI/CD Workflow
1. **Code Change** → 2. **GitHub Commit & PR** → 3. **Cloud Build Trigger** → 4. **Docker Image Built & Pushed** → 5. **Kubernetes Deployment** → 6. **Service Exposure & Monitoring**

---

## Future Improvements
- Implement **logging & monitoring** using Prometheus & Grafana.
- Add **Terraform** for infrastructure as code.
- Improve **CI/CD pipelines** with ArgoCD or Jenkins.

---

## License
This project is licensed under the **MIT License**.
