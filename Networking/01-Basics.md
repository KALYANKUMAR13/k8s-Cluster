
![image](https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/987dc043-9d7a-4790-86d5-a590ef9796df)


Network Namespaces:
Whenever, we are creating container, it has its own namespace, where it can't able to view the other contents. The container has its own routing table, arp table and interface. The container can not able to see the host interface. 

First, we are creating a virtual cable, then attach to particualr network with its ip. Then we adding both networks through virutal cable. While host's does not get any idea, untill it gets connected. 
When we disconnect one end, the other gets disconnected.

![image](https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/1087a58a-4c23-40c6-ab3f-2fc2e5d10783)
