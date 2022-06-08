### This projects aim is to create a wordpress system with mysql database which has a backup volume to keep the database objects persistent, even the database node/pod fails.

* We do provide wordpress credentials such as, auth_key, logged_in_key, secure_auth_key, nonce_key, auth_salt, secure_auth_salt, logged_in_salt, nonce_salt to make the wordpress replicas identical.

* Create an EFS(elastic file system), can either be injected if it exists already;
```
    aws efs create-file-system --creation-token <creationnumber>
```
    - Take the FileSystemId from output and mount in the subnet which is located in the cluster
```
    aws efs create-mount-target --file-system-id <FileSystemId> --subnet-id <subnetIdfromnode> --security-group <securitygroupIdfromnode>
```
