Storage class will automaically creata PV.

First we need to creata Storage Class. Storage class are EBS or Azure Disk storage. 

K8s provides the provisioning of this by storage class.

We don't want to manually create it. Storage class, it under the hood created PV. We will be mentionig the which provider to use.

SC-> PV 

Even though, PV and PVC are created, It won't attach automatically. WHen a pod is attach PVC, then only PV and PVC are attached.
