<img width="867" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/cba04261-3c52-40c4-84a0-0f27d6904b57">
Network Policy:
<img width="737" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/d170ab88-75b3-4b61-8d4d-e0b497e3fdda">

Allowing only backend-api to communicate with the db, this is configured by this. If we configured only ingress part, incoming traffic will from from that service and return the payload to that one. But Same pod cant perfrom egress call to another servies,unless defined.

<img width="309" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/e08df7f3-69f5-4e46-9c85-cbe71fe37847">

Pink is not allowed , unless it is defined



Kubectx and Kubens – Command line Utilities


kubectx is used to change between clusters
kubens is used to change between namespaces

