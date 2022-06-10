### Basic horizontal pod autoscaler example.

* An HPA scaler that scales deployment with %50 cpu utilization. Max replica is determined as 10.
* After the deployment get into running stage you an add load to pods via;
```
    kubectl run -i --tty <name> --image=busybox /bin/sh
    while true; do wget -q -O- http://hpa.example.default.svc.cluster.local:31001; done
```
* Examine through kubectl get hpa to see the workload on pods.