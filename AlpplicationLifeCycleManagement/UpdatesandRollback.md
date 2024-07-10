Whenever we are applying the file, rollout is happening and reference **revison** 1 is created.
Whent the next version of the image is deployed, revison 2 is referenced.

This revison helps to rollback 
```
kubectl rollout history deployment/<deploymentName>
```
This provide the history of rollout to the particualar pod


**ReCreate** deplouyment strategy -> destroy all pods and create new one 


**RollingUpdate** -> delete one pod and replace with new one, delete it one by one and created after each delete(new version) is created  ==This the **default deployment strategy**


![image](https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/75276f8d-8a27-4fe9-892e-143e475169e0)


![image](https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/b4ea455d-0f34-46e1-897a-50814b17b26f)


To rollback to the previous deployment, because current one has some bugs.
```
kubectl rollout undo deployment/<nameOf the Deployment>
```
![image](https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/660ad594-e578-4915-a4ef-64e03b882e85)
