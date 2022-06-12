### This projects aim is to understand affinity/anti-affinity in both pods and nodes.

* Affinity works on pods as well, compared to a nodeSelector.

* Affinity creates rules for pods/nodes to be scheduled and it is only relevant during scheduling. Once the pod/node is created, It should be recreated to apply new rules.

* When writing pod affinity rules most used indentations are;
  - In, NotIn (does a label have one of the values)
  - Exists, DoesNotExist (does a label exist or not)
  - Topology (helps you to define AZ/node/host etc.)

---

* Node affinity is divided into 2;
  * requiredDuringSchedulingIgnoredDuringExecution
  * preferredDuringSchedulingIgnroedDuringExecution(there exist weight parameter which states the rules score/ the highest scored node will be selected as main pod schedule host)

**Run node-affinity.yml with nodes labeled env=dev**
  
---

* Pod affinity is divided into 2;
  * requiredDuringSchedulingIgnoredDuringExecution
  * preferredDuringSchedulingIgnroedDuringExecution

**Run pod-affinity.yml and scale 2nd deployment to observe the pods are only running on the nodes which are also containing 1st deployment. Try it with changing topology as "failure-domain.beta.kubernetes.io/zone" to observe the deployment is also created in nodes which share same AZ(not only ones with 1st deployment).**

---

* Pod Anti-Affinity creates a rules where the pod should not be created.



