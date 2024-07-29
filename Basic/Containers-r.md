Container Runtime Interface(CRI)
Initially, k8s had container runtime named dockershimp, for the purpose of container runtime. Dockershimp has all features of Docker. Then eventually, contianerd the run time of docker has been segerated and used now as runtime environment in k8s orchestration.

In k8s v1.24 they changed to containerd.
