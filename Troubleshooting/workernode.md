First check the kubelet is working in node 

Check the kubelet service is running or not
```
service kubelet status
```

It it is inactive, start it by 
```
service kubelet start
```


If the status is in activating state, some configuration is messed up and need to fix it , Then look the logs of the service. 

```
jornalctl -u kubelet
```


control plane port is 6443
