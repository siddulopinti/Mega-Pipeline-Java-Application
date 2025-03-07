 Mega-Pipeline-Java-Application

 Basic Calculator CI/CD with Kubernetes & Azure DevOps

  Project Overview
This project demonstrates how to build, test, and deploy a **Java-based calculator application** using **Azure DevOps, Kubernetes (AKS), Docker, Prometheus, and Grafana**.

  Tech Stack
- **Java**: Core programming language
- **Docker**: Containerization
- **Azure Kubernetes Service (AKS)**: Orchestration
- **Azure DevOps Pipelines**: CI/CD automation
- **SonarQube**: Code quality & static analysis
- **Prometheus & Grafana**: Monitoring & visualization

  Setup & Deployment

 1️⃣ Prerequisites
- **Azure Subscription** with AKS & ACR enabled
- **Azure DevOps** account
- **GitHub Repository** to host the project

 2️⃣ Clone Repository
```sh
git clone https://github.com/yourusername/Basic-Calculator-CICD-K8s.git
cd Basic-Calculator-CICD-K8s

3️⃣ Build & Push Docker Image
sh
Copy
Edit

docker build -t youracr.azurecr.io/calculator:latest .
docker login youracr.azurecr.io -u <ACR_USERNAME> -p <ACR_PASSWORD>
docker push youracr.azurecr.io/calculator:latest


4️⃣ Deploy to Kubernetes
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
kubectl apply -f kubernetes/prometheus.yaml
kubectl apply -f kubernetes/grafana.yaml


5️⃣ Setup Monitoring

Access Grafana at http://<EXTERNAL_IP>:3000
Add Prometheus as a data source
Import prebuilt dashboards for real-time monitoring

CI/CD Pipeline
The Azure DevOps YAML pipeline automates:

Code Checkout (from GitHub)
Static Code Analysis (SonarQube)
Build & Push Docker Image
Deploy to Kubernetes (AKS)
Enable Monitoring (Prometheus & Grafana)


