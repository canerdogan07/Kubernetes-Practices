kubectl create -f helm-rbac.yml

helm init --service-account tiller

kubectl get pods -n kube-system

helm search redis

helm install --name myredis stable/redis

can be deployed multiple