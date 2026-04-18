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
Start by cloning the repository to your local environment:
```bash
git clone [https://github.com/Ibrahim-Adel15/Docker-1.git](https://github.com/Ibrahim-Adel15/Docker-1.git)
cd Docker-1
```
![](screenshots/1.png) 

### 2. Create the Dockerfile
Create a file named Dockerfile in the root directory of the project with the following configuration:
# Step 1: Use Maven base image with Java 17
FROM maven:3.8.4-openjdk-17 AS build

# Step 2: Create and set the working directory
WORKDIR /app

# Step 3: Copy the application source code into the container
COPY . .

# Step 4: Build the app using mvn package
RUN mvn clean package -DskipTests

# Step 5: Expose port 8080
EXPOSE 8080

# Step 6: Run the app using the generated jar file
ENTRYPOINT ["java", "-jar", "target/demo-0.0.1-SNAPSHOT.jar"]
