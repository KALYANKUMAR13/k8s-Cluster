Monitoring the cluster 

Metrics Server: In memory monitoring, not stored in disk. It is done for each node and its associated manifests.
This is done by  cAdvisor which is in kubelet. 

clone the metics server
```
git clone https://github.com/kodekloudhub/kubernetes-metrics-server.git
```

Deploy the folder

and then run kubrctl commands


```
kubectl top node
kubectl top pods
```


application logs:

If multiple containers in a pod, we need to explicitly tell which container to have log

```
kubectl logs <podName>
```
