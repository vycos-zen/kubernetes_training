# Deployment related commands

## General

### Hiearhy

  - Deployment
    
     - Replica Set
      
       - Pod
        
         - Container

### example deployment

```

apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
  labels:
    app: my-nginx
    tier: frontend
spec:
  replicas: 2
  minReadySeconds: 10
  selector:
    matchLabels:
      tier: frontend
  template:
    metadata:
      labels:
        tier: frontend
    spec:
      containers:
        - name: ny-nginx
          image: nginx:alpine
          resources:
            limits:
              memory: 512Mi
              cpu: "1"
            requests:
              memory: 256Mi
              cpu: "0.2"
          livenessProbe:
            httpGet:
              path: /index.html
              port: 80
            initialDelaySeconds: 15
            timeoutSeconds: 2
            periodSeconds: 5
            failureThreshold: 1
          readinessProbe:
            httpGet:
              path: /index.html
              port: 80
            initialDelaySeconds: 3
            periodSeconds: 5
            failureThreshold: 1
          ports:
            - containerPort: 80


```

## Commands

### to create a deployment

```

kubectl create -f my-nginx.deployment.yaml --save-config

```

### to update existing deployment with rolling updates and zero downtime

```

kubectl apply -f myngix.deployment.yaml

```

### to list existing deployments

```

kubectl get deployments

```

### to display it with labels

```

kubectl get deployment --show-labels

```

### to get a deployment with a specific label use

```

kubectl get deployment -l app=nginx

```

### to delete a deployemnt

```

kubectl delete deployment frontend

kubectl delete -f my-nginx.deployment.yaml

```

### to scale the replics sets 

```

kubectl scale deployment frontend --replicas=5

```