## This projects aim is to show a deployment with mysql database backend.

- There exists a secret file which includes; 
  - username
  - password
  - rootPassword
  - database 

### Database is created as pod which uses the credentials from secret file and exposes through nodeport service on port 3306(which is default).

### Helloworld application exposed as a deployment with 3 replicasets. Marks the created database as its own database, using the same credentials as hardcoded(Just to show the credentials are same, this is not a secure way. It is always safe to keep credentials hidden.)

- Helloworld application counts every visit count and stores the data in mysql database.

We will be checking the mysql database as;

```
    kubectl exec -it <hellowolrd-podname> -- bash
    ## > mysql -u <username> -p<password>
```

If the credentials are correct;

```
    mysql> show databases;
    "Databases table pops up"
    mysql> use <the appname>;
    mysql> show tables;
    mysql> select * from <data collected>;
```

- The helloworld deployment is exposed from both nodeport and loadbalancer services.
