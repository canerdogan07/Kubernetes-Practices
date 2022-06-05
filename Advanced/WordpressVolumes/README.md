* We do provide wordpress credentials such as, auth_key, logged_in_key, secure_auth_key, nonce_key, auth_salt, secure_auth_salt, logged_in_salt, nonce_salt to make the wordpress replicas identical.

* Create an EFS(elastic file system);
```
    aws efs create-file-system --creation-token <creationnumber>
```
    - Take the FileSystemId from output and mount in the subnet same as cluster
```
    aws efs create-mount-target --file-system-id <FileSystemId> --subnet-id <subnetIdfromnode> --security-group <securitygroupIdfromnode>
```