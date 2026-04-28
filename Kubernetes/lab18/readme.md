# 🚀 Lab 18 : Control Pod-to-Pod Traffic using Network Policy


## 🎯 Objectives
- Create a NetworkPolicy resource
- Restrict access to MySQL pods
- Allow traffic only from application pods
- Limit access to port 3306 (MySQL default port)

## 🧠 Key Concepts

### 🔹 NetworkPolicy
A Kubernetes resource used to control how pods communicate with each other and external endpoints.

### 🔹 Ingress Traffic
Incoming traffic to a pod.

## ⚙️ Network Policy Configuration

### 📌 Policy Details

| Field        | Value                |
|--------------|---------------------|
| Name         | allow-app-to-mysql  |
| Pod Selector | app=mysql           |
| Policy Type  | Ingress only        |
| Port         | 3306                |

### 🛠️ NetworkPolicy YAML
```
vim network.yaml
```
![](screenshots/1.png)

### Apply : 
kubectl apply -f network.yaml
```
kubectl apply -f network.yaml
```
![](screenshots/2.png)
