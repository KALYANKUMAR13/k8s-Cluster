If the liveness probe fails, k8s will restart the  container. This helps to ensure the application recovers from problems


If the readiness probe fails, Kubernetes will stop sending traffic to a particular pod by removing the endpoint from the service.

<img width="823" alt="image" src="https://github.com/user-attachments/assets/735fa9ce-93c5-4b0d-9b26-eafd9825c7fc">


Under eaxch probe, we have 3 types of health check. tcpSocket- kubelet will try to open a port on container.

<img width="745" alt="image" src="https://github.com/user-attachments/assets/61184686-552d-4cc7-9681-66b9ae7a19ce">

