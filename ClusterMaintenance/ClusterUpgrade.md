All the components should be less than the API server

APi server
Control Manager and Scheduler -> can be same version of APi server or One version less than that.
kubelet and kubeproxy-> can be same version of APi server or Two version less than that the APi server. 

etcd and coreDns are seperate biniaries
Update the kubelet seperately, it comes under kubeadm, but we need to update
kubectl can be higher than api server or same or less. 

Latest(last) 3 releases are supported by k8s . So upgrade to new release,(current 3 )

First upgrade the master node, and then worker node. 
At  the time of **master node upgrade**, Remaining worker nodes do their activity. We can't have control on any thing during master upgrade. Because API server is down,

Worker node upgrade,
-> updating single node at time, so pods in particaulr node can be placed in other node and perform its functionality.
-> Get the new node with new version(easy in cloud), then drain the old node and deleted.
Master node upgrade
```
apt-get upgrade -y kubeadm=1.X.X
kubeadm upgrade apply v1.X.X
```


The worker node upgrade 
```
kubectl drain <nodename>
apt-get upgrade -y kubeadm=1.X.X
apt-get upgrade -y kubelet=1.X.X
kubeadm upgrade none config --kubelet-version=1.X.X
systemctl restart kubelet

kubectl uncordon <nodeName>
```
Finally we need to uncordon it, because initially we drained, so that pods are evicted safely and node becomes usnscheduleble
