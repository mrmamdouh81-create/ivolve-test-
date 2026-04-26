# 🚀 Lab 15 : Node.js Application Deployment with ClusterIP Service (Kubernetes)

## 📌 Overview

This lab demonstrates how to deploy a **Node.js application on Kubernetes** using a Deployment and ClusterIP Service, while integrating key Kubernetes concepts such as:

- ConfigMap & Secret (environment variables)
- Persistent Volume (PV & PVC)
- Tolerations
- Namespaces
- Load balancing using ClusterIP Service

## 🧱 Architecture

The application is deployed using:

- **Deployment** → Runs Node.js app with 2 replicas
- **ClusterIP Service** → Internal load balancing
- **ConfigMap** → Non-sensitive environment variables
- **Secret** → Sensitive data (e.g., passwords)
- **PersistentVolume (PV)** → Static storage
- **PersistentVolumeClaim (PVC)** → Storage request
- **Toleration** → Allows scheduling on tainted nodes
- **Namespace** → Isolates resources (e.g., dev environment)

## 📦 Prerequisites

- Kubernetes cluster (Minikube / Kubeadm / Cloud)
- kubectl configured
- Docker image pushed to Docker Hub

### 🔐 Step 1: Create ConfigMap from yaml.file
Stores non-sensitive environment variables:
```
vim configmap.yaml
```
![](screenshots/1.png)

### Apply :
```
kubectl apply -f configmap.yaml
```
![](screenshots/2.png)



