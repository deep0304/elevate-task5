# Kubernetes Minikube Deployment Task

## Objective
Deploy and manage applications in a local Kubernetes cluster using **Minikube**.

---

## Tools Used
- Minikube
- kubectl
- Docker

---

## Steps Followed

1. **Start Minikube Cluster**
```bash
minikube start --driver=docker
kubectl get nodes
```
Verified the node is in `Ready` state.

2. **Create Deployment**
- Created `deployment.yaml` for a simple Nginx app with 2 replicas.
```bash
kubectl apply -f deployment.yaml
kubectl get pods
```

3. **Expose Deployment as Service**
- Created `service.yaml` to expose the app on NodePort.
```bash
kubectl apply -f service.yaml
kubectl get svc
```
- Accessed service:
```bash
minikube service demo-service --url
```

<img width="903" height="229" alt="image" src="https://github.com/user-attachments/assets/f04ff066-426d-42df-80c0-ff206235910b" />


4. **Scale Deployment**
```bash
kubectl scale deployment demo-deployment --replicas=4
kubectl get pods
```

<img width="783" height="501" alt="image" src="https://github.com/user-attachments/assets/8ae1042d-555f-4e6a-8eab-60a0e0542288" />


5. **Inspect and Debug**
```bash
kubectl describe deployment demo-deployment
kubectl logs <pod-name>
```

---

## Deliverables
- **YAML Files:** `deployment.yaml`, `service.yaml`
- **Screenshots:**
  - Pods running (`kubectl get pods`)
  - Service details (`kubectl get svc`)
  - Accessed Nginx page in browser
 
     <img width="949" height="308" alt="image" src="https://github.com/user-attachments/assets/d706740f-493b-43cc-b513-60bbb87cd555" />


---

## Outcome
- Learned how to run a local Kubernetes cluster with Minikube.
- Deployed and scaled a simple application using Deployment.
- Exposed the application using Service and verified accessibility.
- Used kubectl commands to inspect, debug, and manage resources.
