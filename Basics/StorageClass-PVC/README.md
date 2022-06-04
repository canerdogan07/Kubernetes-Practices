### This projects aim is to provision StorageClass and PersistentVolumeClaim.

- Rather then linking a volume that is already created before, storageclass sends volume create requests to cloud provider.

- Persistent volume fetchs the request and injects the storage type and limit to request.

- Deployment or pod mounts the volume from persistent volume claim.