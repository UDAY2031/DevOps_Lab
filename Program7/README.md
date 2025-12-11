# Expose Deployment with NodePort & Scale to 3 Replicas 

## 1️⃣ Apply the NodePort Service
```
kubectl apply -f service-nodeport.yaml
```

## 2️⃣ Check the Service
```
kubectl get svc student-portal-nodeport
```

---

## 3️⃣ Get Node IP
```
kubectl get nodes -o wide
```
---
## 5️⃣ Scale Deployment to 3 Replicas
```
kubectl scale deployment student-portal-deploy --replicas=3
```
---
## 6️⃣ Verify Pods
```
kubectl get pods -l app=student-portal
```
