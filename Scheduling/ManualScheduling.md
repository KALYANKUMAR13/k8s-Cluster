Usualy deployment or any manifest, we can add nodeName and mention the particular node.  It can be done before applying to the cluster.
If we need to do after it is deployed, we need to create a bind-definition to it 

nodeName is the sibling of containers


```
---
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  -  image: nginx
     name: nginx
  nodeName: controlplane
```

----
kubectl get pods --selector bu=finance
