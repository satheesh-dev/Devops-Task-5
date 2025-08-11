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
<img width="1524" height="194" alt="Screenshot 2025-08-11 115646" src="https://github.com/user-attachments/assets/294eff4d-5b51-41ec-91e0-d53d197aa0e9" />

### 2. Rolling update status
<img width="1356" height="281" alt="Screenshot 2025-08-11 115912" src="https://github.com/user-attachments/assets/3d6cbf78-53a5-4034-b80a-f1da61c6117f" />

### 3. Service details
<img width="1429" height="910" alt="Screenshot 2025-08-11 121348" src="https://github.com/user-attachments/assets/b7880994-9279-42dc-a533-6fea0826767f" />

### 5. Application in browser
<img width="1730" height="585" alt="Screenshot 2025-08-11 120057" src="https://github.com/user-attachments/assets/e637d3b0-b203-4915-ba22-84e081044a28" />

```bash
minikube start --driver=docker --memory=2000mb
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
minikube service hello-service --url
