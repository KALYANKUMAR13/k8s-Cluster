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

