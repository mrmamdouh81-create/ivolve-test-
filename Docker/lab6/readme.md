# Lab 6 : Managing Docker Environment Variables Across Build and Runtime
This repository demonstrates the practical application of managing environment variables within Docker containers using three different methods: Direct CLI Flags, Environment Files, and Dockerfile ENV instructions.

## 🚀 Objectives
Containerize a Python Flask application.

Understand the precedence and scope of environment variables.

Practice different ways to inject configurations into running containers.

### 🛠️ Implementation Steps
1. Environment Setup
Clone the source code from the repository:
```
git clone https://github.com/Ibrahim-Adel15/Docker-3.git
cd Docker-3
```
![](screenshots/1.png)

### 2. Dockerfile Configuration
The Dockerfile is configured with a base Python image and includes default environment variables for the production environment.
```
vim dockerfile
```
![](screenshots/2.png)

### 3. Building the Image
```
docker build -t mamdouh .
```
![](screenshots/3.png)

### 4. Run the Containers (3 Different Methods)
Method I: Using Command Line Variables (Development)
Inject variables directly using the -e flag:
```
docker run -d -p 8081:8080 --name con2 -e APP_MODE=development -e APP_REGION=us-east mamdouh
```
![](screenshots/4.png)

### Method II: Using an Environment File (Staging)
1. Create a file named env.txt :
```
APP_MODE=staging
APP_REGION=us-west
```
2. Run the container using the --env-file flag:
```
docker run -d -p 8082:8080 --name con3 --env-file env.txt mamdouh
```
![](screenshots/5.png)

### Method III: Using Dockerfile Defaults (Production)
Run the container without any flags; it will use the values defined inside the Dockerfile:
```
docker run -d -p 8080:8080 --name con1 mamdouh 
```
![](screenshots/6.png)




