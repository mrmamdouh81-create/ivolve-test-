# 📘 Lab 16 : Kubernetes Init Container for Pre-Deployment Database Setup

## 🧾 Objective

Modify a Node.js Deployment to include an Init Container that prepares a MySQL database before the application starts.

The Init Container:

Uses MySQL client image
Creates database ivolve
Creates user ivolve_user
Grants full privileges

### 🚀 Step 1 : Create Namespace
```
kubectl create namespace ivolve
```
![](screenshots/1.png)

### 🐬 Step 2 : Deploy MySQL
```
vim mysql.yaml
```
![](screenshots/2.png)

### Apply : 
```
kubectl apply -f mysql.yaml
```
![](screenshots/3.png)

### ⚙️ Step 3 : Create ConfigMap
```
vim config.yaml
```
![](screenshots/4.png)

### Apply :
```
kubectl apply -f config.yaml
```
![](screenshots/5.png)

### 🔐 Step 4 : Create Secret
```
vim secret.yaml
```
![](screenshots/6.png)

### Apply :
```
kubectl apply -f secret.yaml
```
![](screenshots/7.png)

### 🚀 Step 5 : Node.js Deployment with Init Container
```
vim deploy.yaml
```
![](screenshots/8.png)

### Apply : 
```
kubectl apply -f deploy.yaml
```
![](screenshots/9.png)

### 👀 Step 6 : Check Pods
```
kubectl get pods -n ivolve
```
![](screenshots/10.png)

