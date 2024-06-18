**Persistant Volume** : A Persistent Volume (PV) is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using Storage Classes. PVs are cluster resources, similar to nodes, and are independent of the pod lifecycle.

Access Modes: Specifies how the volume can be accessed by pods. Common modes are:
ReadWriteOnce (RWO): The volume can be mounted as read-write by a single node.
ReadOnlyMany (ROX): The volume can be mounted as read-only by many nodes.
ReadWriteMany (RWX): The volume can be mounted as read-write by many nodes.

MountBindinf with host path is not recommended because, Data in one node can't be poplated in another node, as a normally. So use cloud Storages like EBS, Blob.

----


Persistent Volume Cliam : Every PVC is bound to single PV
