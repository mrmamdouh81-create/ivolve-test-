# Lab 8 : Custom Docker Network for Microservices

## 📝 Lab Description
Implementation of a custom Docker bridge network to enable communication between a Flask Backend and two Frontend instances, while demonstrating network isolation.

### 🛠️ Step 1 : clone repo from github
```
git clone https://github.com/Ibrahim-Adel15/Docker5.git
cd Docker5
```
![](screenshots/1.png)

### 🛠️ Step 2 : Preparation of Dockerfiles
#### 1. Frontend Dockerfile (Dockerfile.fe)
#### 2. Backend Dockerfile (Dockerfile.be)
```
vim Dockerfile.fe
vim Dockerfile.be
```
![](screenshots/2.png)

![](screenshots/3.png)

### 🛠️ Step 3 : Deployment & Networking
#### 1. Build Images
```
docker build -f Dockerfile.fe -t front-iamge .
docker build -f Dockerfile.be -t back-image .
```
![](screenshots/4.png)

![](screenshots/5.png)


