 We can have our schedular, so that default schedular will not schedule., we can provide the scheduling alfo.
The kind of type KubeSchedularConfiguration.

The config file should be mentioned as command
 and passed as volumes
```
 kubectl get events -o wide
```
List the events , 

-------------


If the pods needs to be first scheduled, we need to add Priority to the pod. 

Scheduling Plugins:
1. PrioritySort
2. Filtering -> NodeResources Left and Fit, NodeName, NodeUnschedulable
3. Scoring -> scores the nodes based of free space, after the particular pod is assigned to that NOde, ImageLocality -
4. Binding - defaultBinder

Now, in one kubeScheduleConfiguration, we can give mutiple schedulers and its rules.
