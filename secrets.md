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