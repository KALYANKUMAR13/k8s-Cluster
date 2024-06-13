Secrets are only encrypted not encoded. 
So any one can able to decrypt and view it.

Secrets are not encrypted in etcd by default. But we need to add to encryption at rest.


--------

There are 3 common patterns when it comes to designing multi-container PODs. The first, and what we just saw with the logging service example, is known as a sidecar pattern. The others are the adapter and the ambassador pattern.


------------------------


That is a task that will be run only one time when the pod is first created. Or a process that waits for an external service or database to be up before the actual application starts.
