StaticPod means /etc/kubernets/manifests folder=> the yaml manifiest should be inside that folder and need to specifically in the node 

So First ssh into particular node and create a manifest of it 

---------------------------------------------

Whenever a node is not running, check the kubelet is runnning in the node by 
```
journalctl -xe
cat /etc/kubernetes/kubelet.conf
systemctl restart kubelet
```

Dns lookup , go inside the busy box container and nslookup the service.
