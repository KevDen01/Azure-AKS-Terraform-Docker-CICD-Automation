
# AKS Terraform Docker CI/CD Demo

A complete CI/CD pipeline deploying a containerized React Frontend and Flask Backend into Azure Kubernetes Service (AKS) using Terraform for infrastructure provisioning and GitHub Actions for automation.

---

## Project Repositories

[Frontend (React App)](https://github.com/Kevin-Test-K8s/Frontend)  
[Backend (Flask API)](https://github.com/Kevin-Test-K8s/Backend)  
[Terraform Infrastructure](https://github.com/Kevin-Test-K8s/Terraform-Core)

---

## Project Overview

This project demonstrates:
- Automated AKS Infrastructure with Terraform
- Containerized React Frontend and Flask Backend with Docker
- Continuous Integration & Deployment using GitHub Actions
- Secrets Management with Azure Key Vault

---

## Architecture Diagram

```
┌───────────────┐         ┌────────────┐
│   Frontend    │ <────→  │   Backend  │
│  (React App)  │  HTTP   │ (Flask API)│
└───────▲───────┘         └─────▲──────┘
        │                          │
        │                          │
        │    ┌─────────────────┐   │
        └───▶│  Azure AKS      │◀──┘
             │ (Kubernetes)    │
             └────────▲────────┘
                      │
                      │
              ┌───────┴────────┐
              │ Terraform IaC  │
              │  GitHub Actions│
              └────────────────┘
```

---

## Technologies Used

- Azure Kubernetes Service (AKS)
- Terraform (with Remote Backend in Azure)
- Docker
- React (Vite)
- Python Flask
- GitHub Actions

---

## Deployment Steps

### 1. Clone the Repositories
```bash
git clone https://github.com/Kevin-Test-K8s/Frontend.git
git clone https://github.com/Kevin-Test-K8s/Backend.git
git clone https://github.com/Kevin-Test-K8s/Terraform-Core.git
```

### 2. Configure and Deploy Infrastructure
```bash
cd Terraform-Core
terraform init
terraform apply
```

### 3. Deploy Applications
- Push code to the Frontend or Backend repositories.
- GitHub Actions will automatically build Docker images and deploy to AKS.

---

## Secrets and State Management

- Azure Key Vault stores sensitive data such as Storage Account keys.
- Terraform state is securely stored in Azure Storage Account.

---

## Application Access

- Frontend: `http://<AKS_EXTERNAL_IP>/`
- Backend API: `http://<AKS_EXTERNAL_IP>/api/hello`

Replace `<AKS_EXTERNAL_IP>` with your actual Load Balancer or Ingress address.

---

## Author

Kevin Klein Kampmeier  
[LinkedIn](https://www.linkedin.com/in/kevin-klein-kampmeier)  
[GitHub](https://github.com/KevDen01)
