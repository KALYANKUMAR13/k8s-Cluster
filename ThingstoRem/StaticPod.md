StaticPod means /etc/kubernets/manifests folder=> the yaml manifiest should be inside that folder and need to specifically in the node 

So First ssh into particular node and create a manifest of it 

---------------------------------------------

Whenever a node is not running, check the kubelet is runnning in the node by 
```
journalctl -xe
cat /etc/kubernetes/kubelet.conf
systemctl restart kubelet
```
--------------------------------------------
Dns lookup , go inside the busy box container and nslookup the service.

-----------------------------------------------

To know which components of the controlplane are installed through kubeadm. check /etc/kubernetes/manifests/files of component

Command to check anything in the running by system service  
```
find /etc/systemd/system/ | grep kube
```
This gives the services installed on its own.

Usually corendns and network add on is deployed as deployment in kube-system namespace.

