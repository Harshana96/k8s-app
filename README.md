# Kubernetes App Deployment

Deploys the Task Manager app on a Kubernetes cluster using manifest files.

## Manifests

| File | Kind | Purpose |
|------|------|---------|
| backend-pod.yaml | Pod | Single backend pod |
| backend-deployment.yaml | Deployment | 2 replicas with self healing |
| backend-service.yaml | Service | Exposes backend on port 30500 |

## Commands used
```bash
# Apply all manifests
kubectl apply -f backend-deployment.yaml
kubectl apply -f backend-service.yaml

# Check pods
kubectl get pods

# Check services
kubectl get services

# Scale up
kubectl scale deployment backend-deployment --replicas=4

# Scale down
kubectl scale deployment backend-deployment --replicas=2

# Port forward to test locally
kubectl port-forward service/backend-service 5000:5000
```

## What I Learned
- Difference between Pod, Deployment and Service
- How Kubernetes self-heals crashed containers
- How to scale apps up and down with one command
- Writing Kubernetes manifest YAML files
- Using kubectl to manage a cluster