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


