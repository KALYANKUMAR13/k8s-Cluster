<img width="891" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/6b2e6fcd-f906-4eec-9d44-63a9c457c41c">

Install container runtime in all nodes, 
```
https://kubernetes.io/docs/setup/production-environment/container-runtimes/
```

Copy the command for ipv4 packet forwarding, and go for cri, here containerd, 

k8s page will redirect to docker page to install containerd, In the final step , install only containerd alone and check

```
systemctl status containerd
```

On Linux, control groups are used to constrain resources that are allocated to processes. Both the kubelet and the underlying container runtime need to interface with control groups to enforce resource management for pods and containers and set resources such as cpu/memory requests and limits.

cgroupfs is default for containerd, so both containerd and kubelet should have same init system. Both should match.

Go to cgroups section, follow the instructions, go to particulr folder delete all content , save with on k8s page. and restart with sudo 
