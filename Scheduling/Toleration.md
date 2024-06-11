If the node is **tained**, we can't able to deploy on particaulr node, 
But, If we have added **tolerations** in our manifest, it can be deployed to paricular node. 

Here, if tolerations are added, it is not placed in particular node. it can be placed to other nodes as wel, it dependes on other nodes that are availiable(Total Nodes) and Schedular.

Taint and tolerations for only **RESTRICTING**


Master node is always tainted. when cluster is created. 

k describe nodes <nodename> it will says, whether taint is there or not

----------------------------------------------------------------------------
Node Selector

To place the pods, deployment in a particular node. Under the containers sections, we will be adding the labels of the particular node. Lableing the node 
```
kubectl label nodes <node-name> <label-key>=<label-value>

In NodeSelector, we can only specify the particular node. We can't specify mutiple nodes , or condition of the Node
--------------------------------------------------------------------------
 Node Affinity

requiredDuringSchedulingIgnoredDuringExecution
preferedDuringSchedulingIgnoredDuringExecution

As of now, above both are availiable.
In feature, RequiredDuringExecution wil be added
