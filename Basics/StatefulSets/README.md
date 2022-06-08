### This projects aim is to create a statefulset of cassandra image including;
- ReplicaSets
- Lifecycle
- ReadinessProbe
- PersistenVolume
- StorageClass
- Exposure with Nodeport

#### StatefulSets scale up/down from 0>n-1 or n-1>0. They use DNS to find other peers.