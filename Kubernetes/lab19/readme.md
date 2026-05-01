# 🚀 Lab 19 : Node-Wide Pod Management with DaemonSet

## 📌 Objective

Learn how to use a DaemonSet in Kubernetes to ensure a Pod runs on every node in the cluster using node-exporter for monitoring.

## 🧠 Key Concepts
🔹 DaemonSet

A DaemonSet guarantees that one Pod is deployed on each node.

Use cases:

Monitoring agents (e.g., node-exporter)
Logging agents
Security tools

## 🛠️ Implementation Steps

### ✅ 1. Create Namespace
✅ 1. Create Namespace
```
kubectl create namespace monitoring
```
![](screenshots/1.png)

### ✅ 2. Create DaemonSet
```
vim node-exporter.yaml
```
![](screenshots/2.png)

#### Apply :
```
kubectl apply -f node-exporter.yaml
```
![](screenshots/3.png)

### ✅ 3. Verify Deployment
```
kubectl get pods -n monitoring -o wide
```
![](screenshots/4.png)


