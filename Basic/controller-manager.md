Controller-Manager

It manages variour controllers in k8s. Watch the status and situation is not good, Make a remediate it. This happens through the APi server


Node Controller - Monitors the nodes, every 5s. monitor grace period is 40s. Pod eviction timeout is 5m. If the node is not up, pods are created on other nodes, through replicaset
Replication Controller - Wacthes the desired set of pods are running.

All has it own controller,like deployment controller, service controller, cronjob controller, serviceaccount controller, etc.
All this under controller-manager.

By default, all controllers are enabled. We can cutomize to have only particular controllers, In that case, we can run that service.


