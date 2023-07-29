# Pods

## General

### to create a pod config use 

```

apiVersion: v1
kind: Pod
metadata:
  name: my-nginx
  labels:
    app: nginx
    rel: stable
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

### than run a dry run validation with 

```

kubectl create -f nginx.pod.yaml --dry-run=client

```

### prefered way to start is to first create the cluster

```

kubectl create -f nginx.pod.yaml --save-config

```

### to get running pods 

```

kubectl get pods

```

### than later when changes rolled out use

```

kubectl apply -f nginx.pod.yaml

```

### to delete the pod

```

kubectl delete -f nginx.pod.yaml

```

### to get info about pod use either

```

kubectl get pod my-nginx - yaml

kubectl describe pod my-nginx

```

### to terminal into a pod

```

kubectl exec my-nginx -it sh

```