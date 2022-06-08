### This projects aim is to define an ingress.

---

- On minikube ingress-controller is not needed.

    Since the minikube has an addon for ingress which can be enabled;
    ```
        minikube enable addons ingress
    ```
* Intention is to connect to helloworld-v1.example.com and helloworld-v2.example.com which are echoing Hello World! and Hello World1!. Default localhost connection will be resulting empty.

So try; 
```
    curl minikubeip;Port -H "Host: helloworld-v1.example.com
```