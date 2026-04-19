# Lab 5 : Multi-Stage Build for a Node.js App
This repository demonstrates the implementation of a Multi-Stage Dockerfile to build and run an application efficiently. By utilizing multi-stage builds, we optimize the final image size by separating the compilation environment from the execution environment.

## 🚀 Project Objectives
Stage 1 (Build): Use a Maven base image to compile the source code and package it into a JAR file.

Stage 2 (Run): Use a lightweight Java Runtime (JRE) image to run the application, keeping the final image slim and secure.

### 🛠️ Implementation Steps
1. Clone the Source Code
Start by cloning the application repository to your local environment:
```
git clone https://github.com/Ibrahim-Adel15/Docker-1.git
cd Docker-1
```
![](screenshots/1.png)

### 2. Dockerfile Configuration
Create a Dockerfile in the root directory with the following multi-stage setup:
```
vim dockerfile
```
![](screenshots/2.png)

### 3. Build the Image
Build the image and name it app3. Pay attention to the significantly smaller image size compared to a single-stage build.
```
docker build -t app3 .
```
![](screenshots/3.png)

### 4. Run the Container
Launch a container named container3 from the newly created image:
```
docker run -d -p 8080:8080 --name container3 app3
```
![](screenshots/4.png)

### 5. Verification
Test the application by accessing it through your browser or using a terminal command:
```
curl http://localhost:8080
```
![](screenshots/5.png)

### 🧹 Cleanup
Once the testing is complete, stop and delete the container to free up resources:
```
docker stop container3
docker rm container3
```
![](screenshots/6.png)

