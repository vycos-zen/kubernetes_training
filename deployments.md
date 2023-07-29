# Deployment related commands

## Hiearhy

  - Deployment
    
     - Replica Set
      
       - Pod
        
         - Container

to create a deployment

```

kubectl create -f my-nginx.deployment.yaml

```


to list existing deployments

```

kubectl get deployments

```

to display it with labels

```

kubectl get deployment --show-labels

```