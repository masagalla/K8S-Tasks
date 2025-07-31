 ## Mastering Deployments, ReplicaSets & Rollouts in Kubernetes**

### 🎯 **Objective:**

Learn how to manage Kubernetes **ReplicaSets and Deployments**, update Pod templates, view rollout history, and troubleshoot YAML issues.

**PART 1: Working with ReplicaSets**:

 ### **Task 1: Create a ReplicaSet with 3 replicas of NGINX*

 **What is a ReplicaSet in Kubernetes?**

A ReplicaSet ensures that a specified number of identical pod replicas are running at all times.

**Key Purpose**:

To maintain pod availability — if a pod crashes or is deleted, the ReplicaSet will automatically create a new one.

```bash
kubectl create rs nginx-rs --image=nginx --replicas=3
```
![preview](Images/create_replicas1.png)

*You're getting this error because `ReplicaSet (rs)` does not support the `--image` flag with `kubectl create`.*

*The `--image` flag only works with `kubectl create deployment`, not with `replicaset`.*

 **Use `kubectl create deployment` Instead**
```bash
 kubectl create deployment nginx-deployment --image=nginx --replicas=3
 ```
 ![preview](Images/create_replicas3_2.png)

  **Task 2: Update the ReplicaSet YAML to 4 replicas**:

 1. Export and edit:

```bash
kubectl get rs nginx-rs -o yaml > nginx-rs.yaml
```

2. Update:

```yaml
spec:
  replicas: 4
```

3. Apply:

```bash
kubectl apply -f nginx-rs.yaml
```

✅ Verify:

```bash
kubectl get rs
```
![preview](Images/edit_replicas_file_from3to4.png)
![preview](Images/replicas_4.png) 

### 🔹 Task 3: Scale to 6 replicas via command line:


 


```bash
kubectl scale rs nginx-rs --replicas=6
```

✅ Check:

```bash
kubectl get rs
kubectl get pods
```
![preview](Images/replica_scaled_6.png)

## 📦 **PART 2: Managing a Deployment**

### 🔹 Task 1: Create a Deployment
```bash
kubectl create deployment nginx \
  --image=nginx:1.23.0 \
  --replicas=3 \
  --dry-run=client -o yaml > nginx-deploy.yaml
```
![preview](Images/deployment.png

Edit the file:

```yaml
metadata:
  name: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: v1
  template:
    metadata:
      labels:
        app: v1
    spec:
      containers:
      - name: nginx
        image: nginx:1.23.0
```)