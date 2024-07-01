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

--------------------------------------------

nslookup is dnsutils package 
nslookup => used to query the DNS name or its IP address mapping. 

telnet is a network protocol used to provide a command-line interface for communication with a remote device or server

-----------------------------------------------


For serviceaccount 

```
kubeclt auth can-i create pods --as system:serviceaccount:<Namespace>:<serviceaccountName>
kubectl auth can-i get pods --as system:serviceaccount:ops:gitops -n <nameSpace>
```

-----------------------------------------------------------------

When ever, we want the continaerID , First see the pod is scheduled on which node and ssh into a particular node. Then view the running containers by the following commands

```
crictl ps
```

Recreate a container, do like docker with crictl command

To get the event of the pod,,
```
kubectl get events --field-selector involedObject.name=<podName>
```


