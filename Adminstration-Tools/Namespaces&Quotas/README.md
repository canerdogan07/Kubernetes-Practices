### This projects aim is to show and adminstrate the namespaces in kubernetes cluster using quotas.

* New namespace gets created and quotas are defined via running quota.yml file

* You can observe the quotas in the specified namespace with;
```
    kubectl get quota --namespace=<desired-namespace>
```

* Deployment get created with quotas defined. Otherwise the creation of the deployment will be outputting an error.

* You will be observing a difference between the requested replicas of deployment, while the request is 3 replicas, quotas will only allow creating 2 replicas.
--- 
* You can either set a limit quota for default pod/container(containerlimits.yml file can be observed) creations without specifying any quotas and can be observed with the following;
```
    kubectl describe limits <limit-name> --namespace=<desired-namespace>
```
---