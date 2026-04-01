# Lab 11: Namespace Management and Resource Quota Enforcement

This lab demonstrates how to implement resource governance in Kubernetes by restricting the number of Pods within a specific Namespace.

## 📋 Project Overview

The goal is to create a logical isolation layer (Namespace) and enforce a ResourceQuota that limits the maximum number of Pods to 2. We will also verify the enforcement by attempting to exceed this limit.

### 1. Creating the Namespace

We started by creating a dedicated environment for our resources to ensure they are isolated from the rest of the cluster.
```
kubectl create namespace ivolve
kubectl get namespaces
```

