![image](https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/5d184d0a-97e3-4e19-9711-9280e9b3899a)


There will be a agent in each node, and it will talk to each other nodes, for have a toopology of network conf with all the endpoints(each pod)
/opt/cni/bin is the default directory (for binaries of cni plugin)
Cni is contianer network interface
ls /etc/cni/net.d/--- installed cni plugin in out cluster
CNI Plugins:

CNI plugins are responsible for setting up the network for containers.
They handle tasks like IP address allocation, route setting, and DNS configuration.


Network Configuration:

CNI uses a JSON configuration file to specify the desired network setup.
This configuration file is read by the kubelet, which then invokes the CNI plugin to apply the configuration.


CNI in Kubernetes:

Kubernetes uses CNI plugins to manage the network connectivity of pods.
When a pod is created, the kubelet calls the CNI plugin to configure the pod's network namespace.


IPAM weave : 
IP address for pods 
Cni plugin is responsible for this 
CNI has DHCP, host-local plugins which does it 
