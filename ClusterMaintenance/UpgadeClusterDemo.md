```
cat /etc/*release
```
shows the distribution of the server so we can get the package according to the distribution.


UPGRADING THE MASTER NODE:
Based on the distribution get the packages for the node. Replace the verison number from doc.

```
echo "deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /" | sudo tee /etc/apt/sources.list.d/kubernetes.list

curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
```
Then, update it

```
sudo apt-get update
```

Now new package of k8s is present in the server, and choose the verion, that to needed to be installed

```
sudo apt-cache madison kubeadm
```

Choose the version from the above command,  Take the exact four digits from the version availible

Install kubeadm with that version
```
sudo apt-mark unhold kubeadm && \
sudo apt-get update && sudo apt-get install -y kubeadm='1.29.0-1.1' && \
sudo apt-mark hold kubeadm
```


Now kubeadm of new verison is installed. This can be checked only in master node. 
```
kubeadm version
```

Then apply the upgrade. This command should be less than the above version.
```
sudo kubeadm upgrade apply v1.29.0
```

Now Cluster is updated but not Shown because, we need to update the kubelet
```
sudo apt-mark unhold kubelet kubectl && \
sudo apt-get update && sudo apt-get install -y kubelet='1.29.0-1.1' kubectl='1.29.0-1.1' && \
sudo apt-mark hold kubelet kubectl

sudo systemctl daemon-reload
sudo systemctl restart kubelet
```

Make it uncordon, so that it becomes schedulable
```
k uncordon <nodeName>
```
----------------------------------------------------------------------------------------

FOR WORKER NODE

```
ssh@<node>
```

Ssh into particular node.

Same as master node.

WHile upgrading the kubeadm
```
sudo kubeadm upgrade node
```


