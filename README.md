# Task 5 - Minikube Deployment

## Overview
This task demonstrates deploying an Nginx app to a local Kubernetes cluster using Minikube, exposing it via NodePort, scaling replicas, and performing rolling updates.

## Steps Performed
1. Started Minikube with Docker driver (2GB memory)
2. Created `deployment.yaml` for Nginx
3. Created `service.yaml` for NodePort exposure
4. Applied manifests with `kubectl apply`
5. Verified pods, services, and browser access
6. Scaled deployment to 4 replicas
7. Performed rolling update to new Nginx version
8. Captured logs and pod details

## Screenshots
### 1. Pods after scaling
![Pods after scaling](screenshots/pods.png)

### 2. Rolling update status
![Rolling update](screenshots/rolling_update.png)

### 3. Service details
![Service details](screenshots/service.png)

### 4. Pod description
![Pod description](screenshots/pod_describe.png)

### 5. Application in browser
![Nginx welcome page](screenshots/nginx_browser.png)

## How to Run Locally
```bash
minikube start --driver=docker --memory=2000mb
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
minikube service hello-service --url
