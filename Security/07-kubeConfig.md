The kubeconfig file is under .kube folder 

The kubeconfig file has 3 parts 
1. Cluster (Multiple Clusters, multiple cloud, dev, prod)
2. Context --Combines cluster and particular user. 
3. User - User Account, to which we have access to

   In user, if we have tester access to one cluster, In that cluster we can't deploy or delete the resources. Context comines both Tester@DevEnv


![Screenshot (63)](https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/241bccf2-c61c-41b3-ac29-372f1dd17e6b)


The cluster info should have server url and certificate authority file ca.crt

For users, in users sections should thier public and private keys/certifications  admin.key , admin.crt

In context, we can set default namespace too
