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

to get running pods 

```

kubectl get pods

```

than later when changes rolled out use

```

kubectl apply -f nginx.pod.yaml

```

to delete the pod

```

kubectl delete -f nginx.pod.yaml

```

to get info about pod use either

```

kubectl get pod my-nginx - yaml

kubectl describe pod my-nginx

```

to terminal into a pod

```

kubectl exec my-nginx -it sh

```