INstall continaerd, 
1. First Enable IPv4 packet forwarding  on all nodes
2. INstall container and make sure /etc/containerd/config is set properly.

```
cat /etc/*-release
```
Provides the distribution (linux, or)

3.  Download the correct apt repo, v.29 or 1.30. If we need any releases from v1.29.2, download v1.29. and while executing run the correct version. install on all nodes

```
sudo apt-get install -y kubelet=1.29.0-1.1 kubeadm=1.29.0-1.1 kubectl=1.29.0-1.1
```

4. Initiate the kubeadm with proper args, like cidr block forpod, Then it will provide the secret to join for other nodes and initial commands to run for .kube set as Home and its config

   ```
   kubeadm join 192.32.9.6:6443 --token p8lcmf.5cepkyl7liif0d7m \
        --discovery-token-ca-cert-hash sha256:b6460e43f5b1f9f61aa7498022ed06b97717ee0b9caf21f970a6264d9bbb24c0
   ```  
5. Go to other node and join it with master. and now you get nodes but this will be in not ready state.

```
k get nodes
```
6. Install addon - Networking for netorking among nodes and pods. Check which one needed to be installed. 
```
curl -LO https://raw.githubusercontent.com/flannel-io/flannel/v0.20.2/Documentation/kube-flannel.yml
kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml
```
