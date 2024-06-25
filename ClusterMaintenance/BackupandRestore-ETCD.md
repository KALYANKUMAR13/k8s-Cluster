There are tools which can help to backup the all manifest files. Tool name : Velero. THis tool uses APi server and takes backup

We create a new manifest, whcih combines all the deployments(Running resources in the cluster


Etcd-> we can able to take a snapshot of it by command

```
ETCDCTL_API=3 etcdctl snapshot save <filename>
```
A snapshot will be saved in the particular name


```
export ETCDCTL_API=3
```

First export the version
Save the snapshot in  a particular folder ( Providing the certification path is mandatory)

then 
```
ETCDCTL_API=3 etcdctl snapshot save <filename>
etcdctl \
--cacert=/etc/kubernetes/pki/etcd/ca.crt \
--cert=/etc/kubernetes/pki/etcd/server.crt \
--key=/etc/kubernetes/pki/etcd/server.key \
snapshot save /opt/snapshot-pre-boot.db
```
The below information is from the etcd pod in controlplane
```
--trusted-ca-file=/etc/kubernetes/pki/etcd/ca.crt  ---- cacert
--cert-file=/etc/kubernetes/pki/etcd/server.crt   ---- cert
--key-file=/etc/kubernetes/pki/etcd/server.key   ---- key
 ```


-----------

Restoring the backup
```
export ETCDCTL_API=3
etcdctl --data-dir /var/lib/etcd-new  snapshot restore /opt/snapshot-pre-boot.db
```
The --data-dir is the place where we need to place the backup file,  so etcd will get the details from this file 

/var/lib/etcd -This is the default location of the etcd data, 

Append the folder /var/lib/etcd-new in the Volume's path (Not in VolumeMount). So that folder is mounted to the 


----------------------------------------------------------------------------

Directly Updating on the etcd server

ETCDCTL_API=3 etcdctl --endpoints=https://192.4.55.15:2379 --cacert=/etc/etcd/pki/ca.pem --cert=/etc/etcd/pki/etcd.pem --key=/etc/etcd/pki/etcd-key.pem snapshot restore /root/cluster2.db --data-dir /var/lib/etcd-data-new
         

Step 3: Update the systemd service unit file for etcdby running vi /etc/systemd/system/etcd.service and add the new value for data-dir:
Go to particular file update the directory

Change the ownership of the directory 
```
chown -R etcd:etcd /var/lib/etcd-data-new
```

Finally restart the server
```
systemctl daemon-reload 
systemctl restart etcd

------------------------------------------------------------------------------------------------

For copying from the control plane to the basenode=> which have access to all the clusters.   Taks a copy in the controlplane 

From the base node, 
```
scp cluster1-controlplane:/opt/cluster1.db /opt/cluster1.db
scp <nodeName>:<insisdeNOdeLocation> <baseSystemLocation
```


----------------------------------------------------------------------------------------------
Basically we should be in the machine where we have  that particular file
```
 scp /opt/cluster2.db etcd-server:/root
 ```

