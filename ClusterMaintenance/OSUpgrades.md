
Whenever, we need to perform the upgradation of OS to a particular node, We need to DRAIN the particular node.

When we are draining the node, pods in that particular node is transfered to another node. (Internally, pod is deleted in that node and by rs creates pod on another node.) And the particular node becomes UNSCHEDULABE further, until the drain is removed.

The above command is used to drain the node.
```
kubectl drain node01
```


After the os upgrade is done, we need to remove the drain for the node.
Only new pods(manifests) that are yet to deploy will get schedulaed in this  node
```
kubectl uncordon node01
```


```
kubectl cordon node01
```
This command makes the node unschedulable only . This not makes the existing pods to be terminated like **drain** command 
