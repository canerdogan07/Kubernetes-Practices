### Create a config map using file reverseproxy.conf 
```
kubectl create configmap <configmap name> --from-file=reverseproxy.conf
```
* Chechk whether the connection is forwarded as requested by configmap
```
curl loadbalancer -vvvv
```

As a result, we do request to connect nginx(in loadbalancer port), however reverse proxy from configmap forwards the request to Helloworld image in same deployment.

* You may also check the reverseproxy.conf is mounted as volume in container nginx /etc/nginx/conf.d
```
kubectl exec -it hellworld-nginx -c nginx -- bash
cat /etc/nginx/conf.d/reverseproxy.conf
```
This could be useful to enable SSL for the instance