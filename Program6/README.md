# Kubernetes Deployment Commands 

## 1️⃣ Apply the Deployment
```
kubectl apply -f deployment.yaml
```

---

## 2️⃣ Verify Deployment
```
kubectl get deployments
```

---

## 3️⃣ Verify Pod Status
```
kubectl get pods -l app=student-portal
```

---

## 4️⃣ View Pod Logs
```
kubectl logs <pod-name>
```
