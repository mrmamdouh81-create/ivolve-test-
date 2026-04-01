Lab 10: Node Isolation Using Taints in Kubernetes

This project demonstrates the fundamental concept of Node Isolation in a Kubernetes cluster. It covers the entire workflow from provisioning a multi-node cluster to applying Taints and verifying how they control pod scheduling.

📋 Prerequisites
Before you begin, ensure you have the following installed:

    Minikube: Version 1.38.x or higher.

    kubectl: Version 1.35.x or higher.

    Docker: As the container runtime driver.
```
minikube start --nodes 2
```
![](screenshots/1..png)


