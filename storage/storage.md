# Storage

## Commands 

### create a storage

Just as any other file, YAML config can be applied

```

kubectl create -f [file-name].service.yaml --save-config

```

## Valid storage types

  - DirectoryOrCreate
  - Directory
  - FileOrCreate
  - File
  - Socket
  - CharDevice
  - BlockDevice

## Persistent volume

The persistent volume is cluster wide, persist through the lifecycle of the Pods

## Ephemeral storage

It only stays up through the life sycle of the POD
