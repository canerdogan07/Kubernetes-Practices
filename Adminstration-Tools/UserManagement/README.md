### This projects aim is to create/add users and give them permissions using RBAC as authorization mode.

* Start by adding/creating users via ssh to minikube. Create a key and certificate for the user.
```
openssl genrsa -out -<username>.pem 2048
openssl req -new -key -<username>.pem -out <usernames>-csr.pem -subj "/CN=<username>/0=<teamname>/"
sudo openssl x509 -req -in <username>-csr.pem -CA /var/lib/localkube/certs/ca.crt -CAkey /var/lib/localkube/certs/ca.key -CAcreateserial -out <username>.crt -days 10000
```
* You may check whether it is created via; ls> cat <username>.pem
* Add created key and certificate names into config file via "vim ~/.kube/config" under users section.
* Also add the referenced users key and certificate in minikube folder via copy/paste the created code through process "vim ~/.minikube/<username>.key" and "vim ~/.minikube/<username>.crt
* To check which user is controlling kubectl commands "kubectl config view"
* If the minikube default authorization is not selected as RBAC you want to change it;
  ```
  minikube start --extra-config=apiserver.Authorization.Mode=RBAC
  ``` 
* To connect to cluster with new user, new context should be added.Watched with "kubectl config get-contexts" and can be switched with "kubectl config use-context <username>";
```
kubectl config set-credentials <username> --client-certificate=edward.crt --client-key=<username>.pem
kubectl config set-context <username> --cluster=kubernetes.<clusternames> --user <username>
```
* Now the user is set but the user permissions are not, which will be defined with ClusterRoleBinding(admin-user.yaml file) for cluster wide permission or Role&RoleBinding(user.yaml file) for namespace wide permissions.