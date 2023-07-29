This is a sandbox for kubernetes training core concepts

to create a pod config use 

```

apiVersion: v1
kind: Pod
metadata:
  name: my-nginx
spec:
  containers:
    - name: ny-nginx
      image: nginx:alpine

```

than run a dry run validation with 

```

kubectl -f nginx.pod.yaml --dry-run=client

```

prefered way to start is to first create the cluster

```

kubectl create -f nginx.pod.yaml --save-config

```

than later when changes rolled out use

```

kubectl apply -f nginx.pod.yaml

```