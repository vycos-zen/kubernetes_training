# Secrets

Handle sensitive data on the cluster

## Commands

#### Create a generic secret in command line

```

kubectl create secret generic [secret-name]
  --from-literal=[key]=[value]

```

### Create from file

```

kubectl create secret generic [secret-name]
  --from-file=[key]=[path-to-file]

```

### Create from a key pair

```

kubectl create secret tls [tls-secret] --cert+path=[path-to-file]

```

### Get secrets

```

kubectl get secrets

```

### get secret from YAML 

```

kubectl get secrets db-passwords -o yaml

```