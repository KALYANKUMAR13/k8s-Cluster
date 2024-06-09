Kube-API Server
Whenever, we enter command from CLI(kubectl commmands), this authenticates, and the information is retrived from etcd and response to sent to CLI.


Whenever we are deploying a manifest, it is authenticated by API server and information is updated in etcd, and then return to API server, The Scheduler continously monitors the API server and tells the Node to the API server and then the APi server updates the node information in the etcd and Then finally passes the information to the kubelet in the NOde.

