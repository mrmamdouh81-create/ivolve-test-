# Lab 3: Containerizing a Java Spring Boot Application

This laboratory focuses on the process of containerizing a Java Spring Boot application using Docker. You will learn how to write a Dockerfile, build an image, and manage the lifecycle of a container.

## 📋 Prerequisites

* **Docker** installed and running on your machine.
* **Git** installed for cloning the repository.
* Basic understanding of Docker commands and Java application structure.

## 🚀 Lab Objectives

1.  Clone the application source code.
2.  Develop a professional `Dockerfile` using a Maven base image.
3.  Build a Docker image from the source code.
4.  Run and test the application within a container.
5.  Cleanup the environment.

---

## 🛠️ Step-by-Step Instructions

### 1. Clone the Application Code
Start by cloning the repository to your local environment :
```bash
git clone [https://github.com/Ibrahim-Adel15/Docker-1.git](https://github.com/Ibrahim-Adel15/Docker-1.git)
cd Docker-1
```
![](screenshots/1.png) 

### 2. Create the Dockerfile
Create a file named Dockerfile in the root directory of the project :
```
vim dockerfile
```
![](screenshots/2.png)

### 3. Build the Docker Image
Build the image and name it app1 :
```
docker build -t app1 .
```
![](screenshots/3.png)

### 4. Run the Container
Start a container named container1 using the app1 image, mapping the host port 8080 to the container port 8080 :
```
docker run -d -p 8080:8080 --name container1 app1
```
![](screenshots/4.png)

### 5. Test the Application
Open your web browser or use curl to verify the application is running:
```
URL: http://localhost:8080
Command: curl http://localhost:8080
```
![](screenshots/5.png)

### 6. Cleanup
Once you have finished testing, stop and remove the container :
```
docker stop container1
docker rm container1
```
![](screenshots/6.png)

