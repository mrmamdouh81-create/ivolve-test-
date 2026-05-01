# 🔐 Lab 20 : Securing Kubernetes with RBAC and Service Accounts

## 📌 Objective

In this lab, we will secure Kubernetes access using RBAC (Role-Based Access Control) by:

Creating a ServiceAccount
Defining a Role with limited permissions
Binding the Role to the ServiceAccount
Validating restricted access to cluster resources

## 🧠 Key Concepts
🔹 RBAC (Role-Based Access Control)

RBAC is a security mechanism in Kubernetes that controls:

Who can access the cluster (ServiceAccount)
What they can do (Role)
Where they can do it (Namespace scope)
Binding between them (RoleBinding)

## 🛠️ Implementation Steps

### ✅ 1. Create Namespace
```
kubectl create namespace ivolve
```
![](screenshots/1.png)

### ✅ 2. Create ServiceAccount
```
kubectl create serviceaccount jenkins-sa -n ivolve
kubectl get sa -n ivolve
```
![](screenshots/2.png)

### ✅ 3. Generate ServiceAccount Token
```
kubectl create token jenkins-sa -n ivolve
```
![](screenshots/3.png)

### ✅ 4. Create Role (Read-Only Access)
```
vim role.yaml
```
![](screenshots/4.png)

### Apply :
```
kubectl apply -f role.yaml
```
![](screenshots/5.png)

### ✅ 5. Create RoleBinding
```
vim rolebending.yaml
```
![](screenshots/6.png)

