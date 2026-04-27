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

### 🧪 Step 7 : Verify MySQL
```
kubectl exec -it mysql-66b9f649cc-58vlv -n ivolve -- mysql -u root -proot
SHOW DATABASES;
SELECT user, host FROM mysql.user;
```
![](screenshots/11.png)

![](screenshots/12.png)

### 📌 Summary 

This lab demonstrates how to use an Init Container in Kubernetes to prepare a database environment before starting an application.

A MySQL pod is deployed using MySQL, along with a Node.js application using Node.js. The Init Container runs before the main container and ensures the database is ready.

It connects to MySQL using credentials provided via ConfigMap and Secret, then:

Creates a database named ivolve
Creates a user ivolve_user
Grants full privileges on the database

After successful execution, the Node.js container starts normally.

🧠 Key Idea

Init Containers ensure that all dependencies (like databases) are fully ready before the application starts, improving reliability and preventing startup failures.

