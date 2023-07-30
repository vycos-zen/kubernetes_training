# Services
 
## Commands 

### port forwarding setup on pod

to expose internal services to extrnal communication

```

kubectl port-forward pod/[pod-name] 8080:80

```

### port forwarding on deployment

```

kubectl port-forward deployment/[deployment-name] 8080:80

```

### port forwarding on service

```

kubectl port-forward service/[service-name] 8080:80

```