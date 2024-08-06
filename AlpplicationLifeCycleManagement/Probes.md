If the liveness probe fails, k8s will restart the  container. This helps to ensure the application recovers from problems

LIVENESS Probe -> endpoint in the application, check it and say the application is ready, if not pod deleted and recreated.

If the readiness probe fails, Kubernetes will stop sending traffic to a particular pod by removing the endpoint from the service.

<img width="823" alt="image" src="https://github.com/user-attachments/assets/735fa9ce-93c5-4b0d-9b26-eafd9825c7fc">

READINESS PROBE:
A readiness probe checks whether an application within a pod is ready to handle traffic. If the readiness probe fails, Kubernetes removes the pod from the list of endpoints for the corresponding service, ensuring that no traffic is sent to the pod until it becomes ready again. This is useful for managing rolling updates and ensuring that only healthy pods receive traffic.

Under each probe, we have 3 types of health check. tcpSocket- kubelet will try to open a port on container.

<img width="745" alt="image" src="https://github.com/user-attachments/assets/61184686-552d-4cc7-9681-66b9ae7a19ce">

