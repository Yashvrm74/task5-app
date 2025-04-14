# 🐳 Node.js App on Kubernetes using Minikube

This project demonstrates how to containerize and deploy a simple Node.js application to a local Kubernetes cluster using **Minikube**, **kubectl**, and **Docker**.

---

## 📁 Project Structure

```
.
├── app/
│   └── index.js          # Simple Node.js app (Hello World)
├── Dockerfile            # Docker config for the Node.js app
├── deployment.yaml       # Kubernetes Deployment manifest
├── service.yaml          # Kubernetes Service manifest (NodePort)
└── README.md
```

---

## ⚙️ Tools Used

- **Minikube** (local Kubernetes cluster)
- **kubectl** (Kubernetes CLI)
- **Docker** (for building the container)
- **Node.js** (web server)
- **Ubuntu (on EC2)** (environment used)

---

## 🚀 Getting Started

### 1. Start Minikube
```bash
minikube start --cpus=2 --memory=4096
```

### 2. Build Docker Image
```bash
eval $(minikube docker-env)
docker build -t nodeapp:1.0 ./app
```

### 3. Deploy to Kubernetes

Apply the deployment and service:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### 4. Verify Resources
```bash
kubectl get pods
kubectl get services
```

---

## 🌐 Access the App

Use `kubectl port-forward` to access the Node.js app on localhost:

```bash
kubectl port-forward pod/<pod-name> 8080:3000
```

Then open another terminal and test:

```bash
curl http://localhost:8080
```

---

## 📦 Scale the Deployment

```bash
kubectl scale deployment nodeapp-deployment --replicas=4
kubectl get pods
```

---

## 📋 Describe and Logs

```bash
kubectl describe pod <pod-name>
kubectl logs <pod-name>
```

---

## 📸 Screenshots

Include screenshots of:
- `kubectl get pods`
- `kubectl get services`
- `curl` result
- `kubectl scale`
- `kubectl describe`
- `kubectl logs`

---

## ✅ Deliverables

- `deployment.yaml`
- `service.yaml`
- Screenshots
- This README

---

## 🙌 Author

Your Name – [@yourgithub](https://github.com/yourgithub)

---
