When do don't have cluster, Can we deploy an application.

Yes, If we have kubelet alone in a VM, it periodically monitors the below folder. 

```
/etc/kubernetes/manifest
```

or in the kubeconfig.yaml
In yaml file the above path is mentioned 

When we create a pod like this is called static pod. 

Only Pods can be created, ! RS, Deployment are not able to created

Ignored by Kube-Scheduler
