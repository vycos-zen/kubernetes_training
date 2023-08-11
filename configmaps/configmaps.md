# ConfigMap

## Description

Store configuration data across Pods in a cluster

## Comands

### Create with saved config

Creates configuration from a provided Yaml file, and stores the configuration on the cluster.

```

kubectl create -f [file-name].configmap.yaml --save-config

```

### Create from external file

Read from a file into the ConfigMap

```
//example.config

objective=bread
attempts=8
bread.complete=false
bread.creation.progressState=gathering_resources

```

Create the configuration map in the cluster

```

kubectl create configmap [configmap_name] --from-file=[path-to-file]

```

Create from env file

```
//objectiveConfig.env

objective=bread
attempts=8
bread.complete=false
bread.creation.progressState=gathering_resources

```

```

kubectle create configmap [configmap_name] --from-env-file=[path-to-file]

```

### Create from command line

```

kubectl create configmap [configmap-name]
  --from-literal=apiUrl=http://example
  --from-literal=exampleValue=exampleValue

```