1. Clone the repo, vagrant up . It will take 10 mins
2. Download ssh client tools, so that we can navigate all machine easily. OR List the running vms by command 
```
vagrant global-status
```
and enter to each by  vagrant ssh <Name of the VM>

3.  Inside vagrant folder, private_key for all machines are availiable, connect to all with the

NAT Network (10.0.2.x): Virtualization software often assigns IP addresses in the 10.0.2.x range to virtual machines using NAT. This allows VMs to access the internet via the host machine's IP address.
Host-Only Network (192.168.56.x): IP addresses in this range are assigned to virtual machines for communication between the host and VMs without providing internet access.

4. Generating ssh key  in master-1(Consider any one as master initially, which communicates with all other nodes), so that we can have configure to other node in the cluster and access it using the master and we can transfer the files.
```
ssh-copy-id <Username>@<IPAddress>
ssh-copy-id vagrant@192.168.56.12
```
After doing this, you can enter to master-02 
```
ssh vagrant@<Ipaddress>
```
5. Install kubectl , The kubectl command line utility is used to interact with the Kubernetes API Server. Modifying the permission, making kubectl executable and moving to /usr/local/bin
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/${ARCH}/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

kubectl version  --client
```
The final command shows the version of kubectl
