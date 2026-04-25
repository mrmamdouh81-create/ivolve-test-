# 🚀 Kubernetes Persistent Storage Lab

This project demonstrates how to configure persistent storage in Kubernetes using **Persistent Volumes (PV)** and **Persistent Volume Claims (PVC)** with the `hostPath` storage type.

## 📋 Scenario
We need to set up a persistent storage solution for application logging. The logs should be stored on the node's file system and remain available even if the Pod is deleted.

## 🛠️ Implementation Steps

### 1. Node Preparation
First, we create the physical directory on the worker node and set the appropriate permissions to allow Kubernetes to write data.
```
sudo mkdir -p /mnt/app-logs
sudo chmod 777 /mnt/app-logs
```
![](screenshots/1.png)

### 2. Define Persistent Volume (PV)
The PV represents the actual storage resource in the cluster.
```
vim pv.yaml
```
![](screenshots/2.png)

### 3. Define Persistent Volume Claim (PVC)
The PVC is the request for storage by the user/application.
```
vim pvc.yaml
```
![](screenshots/3.png)

### 🚀 Deployment Commands
Apply the configurations to your cluster:
```
kubectl apply -f pv.yaml
kubectl apply -f pvc.yaml
```
![](screenshots/4.png)

![](screenshots/5.png)

