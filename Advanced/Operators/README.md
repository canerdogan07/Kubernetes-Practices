### This projects aim is to learn about operators in kubernetes cluster. Bring a wide perspective to understand managed services in Kubernetes and cloud such as Managed MYSQL CLuster on AWS cloud.

* Create a storage first via storage.yml
* Run quicstart.sh script to create the necessary files for creation of the operator such as rbac, serviceaccounts, services, secrets, configmaps and deployments.
* Port-forward to the service to use the operator pgo which stands for postgresoperator.(from localhost to kubernetes operator.). Keep the port-forward up for connection to remain.
* You have to place the operator CLI to your PATH from default location. You can use set-path.sh

---

* Now you have to restart. And check whether the connection of operator works. You can check via pgo version which will be resulting => pgo client version 3.1 \n apiserver version 3.1
* Create and show postgres sql cluster with command;
```
    pgo create cluster mycluster
    pgo show cluster all
```
* You can still use kubectl commands.
* Connect to postgres sql;
```
kubectl run -it -- rm --image=postgres:10.4 psql -- psql -h mycluster -U postgres -W
```
---

* You can either scale up the cluster and create a read replica => "pgo scale mycluster"
* Try a failover scenario;
```
    pgo failover mycluster --target=mycluster-<primaryclustername>
```
    Observe the primary cluster name has shifted to the other replica and another replica has spun up!

---

* Failover task that has been applied is a CRD which can be observed via;
```
kubectl get pgtask mycluster-failover -o yaml
```
* You can also observe other CRD's with kubectl get crd