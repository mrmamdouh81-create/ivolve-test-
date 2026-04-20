# Lab 7 : Docker Storage Management (Volumes vs. Bind Mounts)
This lab demonstrates how to manage persistent data in Docker using Named Volumes for logs and Bind Mounts for custom web content.

## 🚀 Overview
In this lab, we use an Nginx server to explore two types of storage:

1. Docker Volume: Used for /var/log/nginx to ensure logs persist even if the container is deleted.

2. Bind Mount: Used for /usr/share/nginx/html to link a local directory on your host to the container for real-time code updates.

### 🛠️ Step-by-Step Implementation
1. Create a Managed Volume
Create a volume named nginx_logs to store Nginx access and error logs.
```
docker volume create nginx_logs
```
![](screenshots/1.png)

### 2. Prepare the Host Directory (Bind Mount)
Create a directory structure on your local machine and add a custom HTML file.
```
mkdir -p nginx-bind/html
echo "Hello from Bind Mount" > nginx-bind/html/index.html
```
![](screenshots/2.png)

