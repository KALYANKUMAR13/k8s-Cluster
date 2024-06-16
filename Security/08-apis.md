There are 2 major APis running in k8s 
1. Core
2. Named

<img width="573" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/9399322d-71e3-4575-97e7-956df30a03f7">


<img width="931" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/b39c055f-e7e9-439b-a550-b560ed970641">


Instead of requesting the api server, a proxy (**kubectl Proxy**) serves on 8001 port by default, which will forward the request to API server.
