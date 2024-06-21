If conifured to particular pod, that particular service is availiable all over the cluster. But dependes on the service type, it makes it visibility outside the cluster.

In NodePort service type, how all the nodes able to open a particular port to a service.
Services are clusterwide concept. (Virtual Object).

Kube-proxy watches kub-api server and do the things

When ever service is created, kubeproxy add the forward to ip  address to the pod (Forward IP)

This is done by kube-proxy's userspace, iptables and ipvs.

in kube-APi server, there a is a range of ip defiend for service (--service-cluster-ip-range => by default 10.0.0.0/24)
Ip tables: 
