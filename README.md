## Description

This project demonstrates how to deploy a **MongoDB database** and **Mongo Express** web interface using **Kubernetes** on a local environment with **Minikube**.
The project uses container images from Docker Hub and deploys them using Kubernetes YAML configuration files.

### Dependencies

Install the following tools:

### 1. Install Chocolatey (Windows Package Manager)

Follow instructions from:
https://chocolatey.org/install

### 2. Install Kubectl

choco install kubernetes-cli

### 3. Install Minikube

choco install minikube

### 4. Enable Hyper-V from Windows Features

### Executing program

#### Start Kubernetes Cluster
```
minikube start
```

#### Apply Kubernetes configuration files in order:
```
kubectl apply -f secret.yaml
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo-app.yaml
kubectl apply -f web-app.yaml
kubectl apply -f mongo-pv.yaml
kubectl apply -f mongo-pvc.yaml
kubectl apply -f mongo-resource-patch.yaml
kubectl apply -f mongo-probes-patch.yaml
kubectl apply -f webapp-patch.yaml
```

### Access Mongo Express UI
```
minikube service webapp-service
```

This gives you the required IP for your service. Run it on port no 30100 and access the Mongo Express UI
