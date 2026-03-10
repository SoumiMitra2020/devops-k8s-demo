# DevOps CI/CD Pipeline with Jenkins, Docker, and Kubernetes

## Overview

This project demonstrates a complete **DevOps CI/CD pipeline** that automatically builds, pushes, and deploys a containerized application to Kubernetes.

The pipeline integrates:

* Git-based source control
* Automated builds
* Containerization
* Continuous deployment to Kubernetes

The goal of this project is to simulate a **real-world DevOps workflow** used in modern cloud-native environments.

---

## Technologies Used

* GitHub – Source code repository
* Jenkins – CI/CD pipeline automation
* Docker – Containerization
* Docker Hub – Image registry
* Kubernetes – Container orchestration
* Minikube – Local Kubernetes environment

---

## Architecture

```
Developer
   │
   ▼
GitHub Repository
   │
   ▼
Jenkins Pipeline
   │
   ├── Build Docker Image
   ├── Push Image to DockerHub
   └── Deploy to Kubernetes
            │
            ▼
      Kubernetes Cluster (Minikube)
```

---

## Project Structure

```
devops-k8s-demo
│
├── app/                  # Node.js demo application
│
├── k8s/                  # Kubernetes manifests
│   ├── deployment.yaml
│   └── service.yaml
│
├── Dockerfile            # Docker image build file
│
├── Jenkinsfile           # Jenkins CI/CD pipeline
│
└── README.md             # Project documentation
```

---

## CI/CD Pipeline Workflow

The Jenkins pipeline performs the following stages:

1. **Clone Repository**

   * Jenkins pulls the latest code from GitHub.

2. **Build Docker Image**

   * The application is packaged into a Docker container.

3. **Push Image to DockerHub**

   * The built image is uploaded to DockerHub.

4. **Deploy to Kubernetes**

   * Kubernetes manifests are applied to deploy the application.

---

## Jenkins Pipeline

The pipeline is defined in the `Jenkinsfile`.

Example stages:

```
Clone Repository
Build Docker Image
Docker Login
Push Docker Image
Deploy to Kubernetes
```

---

## Running the Application

After deployment, the application can be accessed via Kubernetes service.

### Get service information

```
kubectl get svc
```

Example output:

```
demo-service   NodePort   80:30007/TCP
```

### Get Minikube IP

```
minikube ip
```

Example:

```
192.168.49.2
```

### Open the application

```
http://192.168.49.2:30007
```

---

## Verify Deployment

Check running pods:

```
kubectl get pods
```

Check services:

```
kubectl get svc
```

Check deployments:

```
kubectl get deployments
```

---

## Key DevOps Concepts Demonstrated

* CI/CD pipeline automation
* Infrastructure as Code (Kubernetes manifests)
* Containerization with Docker
* Image registry management
* Kubernetes deployment
* DevOps workflow integration

---

## Future Improvements

Possible enhancements:

* Add GitHub Webhooks for automatic pipeline triggers
* Use Helm charts for Kubernetes deployment
* Add monitoring with Prometheus and Grafana
* Implement container security scanning
* Deploy to a cloud Kubernetes cluster (AWS EKS / GKE / AKS)

---

## Author

Soumi Mitra

DevOps Engineer Project – CI/CD Pipeline with Jenkins, Docker, and Kubernetes.
