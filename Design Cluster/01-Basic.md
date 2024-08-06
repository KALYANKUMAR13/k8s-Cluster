
<img width="668" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/548b092f-3781-48b2-8141-bdfe80eea492">



Choices:

Minikube- Under the hood, it deploys a VM - Single nood.

Kubeadm - Requires VM to be ready, we should provision the vm.

**Turnkey Solutions:**

We Provision the VM, configure it, use scripts to deploy cluster, maintaining the vm ourself. Example - kOPs. Cluster management and maintenance are easy.

**Hosted Solutions:**

Kubernetes as a Solutions, GKE, AKS, EKS

<img width="880" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/c626cfe6-a2e3-4c59-ae13-4d80161e5a16">


<img width="854" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/8014e47e-1f6e-432a-b2cb-5e52570992b0">


Configuring etcd in high availiability

etcd, read in all master nodes, write in one node, so in multiple master nodes, one etcd is elected as **leader** and other master nodes becomes follower, 

So any writing request comming to other nodes(Non-leader node) are re-directed to leader node to write. Leader also make sure that other nodes are getting same data after it writes here.

**Leader ELECTION:**  => This is done by RAFT protocal,
A random timer is send to other nodes by each node, the first one to finishes it and send requests to other node to became a leader. Then the other nodes responds by providing the vote and leader is eleted. Fequently, the leader node sends to other nodes, that it is continuing the leader.

After writing, it should send the data to other master nodes, then only 1 work is completed.

Total master nodes/2 Plus 1.

<img width="953" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/61b55bf1-8c67-4998-8575-97dc32dea9c8">



Write is completed, when it can send the data on the **majority of the nodes**,Total master nodes/2 Plus 1.


