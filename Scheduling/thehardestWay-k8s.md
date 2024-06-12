1. Clone the repo, vagrant up . It will take 10 mins
2. Download ssh client tools, so that we can navigate all machine easily. OR List the running vms by command 
vagrant global-status
and enter to each by  vagrant ssh <Name of the VM>
3.  Inside vagrant folder, private_key for all machines are availiable, connect to all with the

NAT Network (10.0.2.x): Virtualization software often assigns IP addresses in the 10.0.2.x range to virtual machines using NAT. This allows VMs to access the internet via the host machine's IP address.
Host-Only Network (192.168.56.x): IP addresses in this range are assigned to virtual machines for communication between the host and VMs without providing internet access.

4. Generating ssh key  in master-1(Consider any one as master initially, which communicates with all other nodes), so that we can have configure to other node in the cluster and access it using the master and we can transfer the files.

ssh-copy-id <Username>@<IPAddress>
ssh-copy-id vagrant@192.168.56.12

After doing this, you can enter to master-02 
ssh vagrant@<Ipaddress>

Choose a master node and perform the steps
5. Install kubectl , The kubectl command line utility is used to interact with the Kubernetes API Server. Modifying the permission, making kubectl executable and moving to /usr/local/bin

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/${ARCH}/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

kubectl version  --client
-------------------------------------------------------------------------------------------------
User in k8s = Private key + Digital Certificate, and presented to api
By default, user will have admin privilage 
To issus a Certificate signing requests

openssl genrsa -out privatekey.pem 2048
openssl req -new -key privatekey.pem -out output.csr


Then create  CertificateSigningRequest yaml file and deploy it and approve the user, Then create Cluster role and Cluster role binding with particular user.

kubectl auth can-i create pods --user=mark
kubectl auth can-i create pods --as=mark

if mark is not in the kubeconfig file, then the first command will not say yes, even though the user has permissions.
If the user is not is kubeconfig file, use as 
-------------------------------------------------------------------------------------------------------
6. Generating CA for all components in k8s
https://github.com/mmumshad/kubernetes-the-hard-way/blob/master/docs/04-certificate-authority.md
Follow the steps and command to generate certificates

10.0.2.15 
192.168.56.11
192.168.56.12
192.168.56.30

kubeconfig file, all other components of k8s will communicate to API server with the help of kubeconfig file. Generating kubeconfig files for all other components, so that other components will able to communicate with APi server. We are configuring the Lb , so that other nodes while trying to communicate, it has support high availability the IP address(particular master)

7.Generating the Data Encryption Config and Key for componets of k8s:
https://github.com/mmumshad/kubernetes-the-hard-way/blob/master/docs/05-kubernetes-configuration-files.md
Generate the kubeconfig files for the componets of k8s and distribute to particular servers -> master kubecong files i.e (admin.kubecofig,kube-controler-manger, kube-scheduler) to master nodes and worker kubeconfig files  i.e kubeproxy.

In Kubernetes (k8s), data encryption is critical for securing sensitive information such as secrets, configuration files, and other confidential data stored within the cluster. The Data Encryption Configuration and Key are used to provide this encryption. Here's a breakdown of why this is needed and how it works:

8.Why is Data Encryption Needed in Kubernetes?
https://github.com/mmumshad/kubernetes-the-hard-way/blob/master/docs/06-data-encryption-keys.md
Security of Sensitive Data:
Secrets: Kubernetes stores secrets (e.g., API keys, passwords, certificates) in etcd, its distributed key-value store. If etcd is compromised, unencrypted secrets can be easily accessed.
Configuration Files: Configuration files may contain sensitive information that needs to be protected.

9.Bootstrapping the etcd Cluster
https://github.com/mmumshad/kubernetes-the-hard-way/blob/master/docs/07-bootstrapping-etcd.md
Kubernetes components are stateless and store cluster state in etcd. In this lab you will bootstrap a two node etcd cluster and configure it for high availability and secure remote access.

If you examine the command line arguments passed to etcd in its unit file, you should recognise some of the certificates and keys created in earlier sections of this course.
RUn in all master nodes, 

10. Install kube controlplane -k8s controller binaries in all master node, Kubernetes API Server, Scheduler, and Controller Manager are downloaded from the kubecontroller 
https://github.com/mmumshad/kubernetes-the-hard-way/blob/master/docs/08-bootstrapping-kubernetes-controllers.md

11. 



for instance in node01; do
  scp node01.key node01.crt node01.kubeconfig ca.crt kube-proxy.crt kube-proxy.key ${instance}:~/
done
