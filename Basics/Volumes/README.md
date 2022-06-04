

- Spin up a cluster.
```
    eksctl create cluster --name <clustername> --nodegroup-name <nodegroupname> --node-type t2.micro --nodes 5
```


- Create a volume
```
aws ec2 create-volume --size 10 --region eu-central-1 --availability-zone eu-central-1a --volume-type gp2 --tag-specifications 'ResourceType=volume, Tags=[{Key=KubernetesCluster, Value=kubernetes.newtech.academy}]'
```
Take the volumeID created.

- Inject it in volumeex.yml "VolumeID: <volumecreated>"

- Apply yml file and exec into pod to create a volume to check if it lives after pod dies and recreates.

```
    kubectl exec <podname> -it -- bash
    ## echo 'test' > /myvol/myvol.txt
    ## exit
    kubectl drain <node of deployment>
```
- When done, do not forget to delete the volume created.

```
    aws ec2 delete -volume --volume-id <volumecreated>
```