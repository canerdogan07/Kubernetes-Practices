### This projects aim is to give information about node decommissions while shutting down nodes.

* Node is registered by kubelet itself.
* To shut down a node, it is better to decommision the node with draining.
```
kubectl drain <nodename> --grace-period=600
```

* You can force the shutdown if the node does not have any controlled pods(replicasets etc.) inside

```
kubectl drain <nodename> --force
```