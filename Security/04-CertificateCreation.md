There are several tools to generate the keys and certificates.
Like : Openssl, EasyRSA and CFssl

CA key and certificate is first generated, so that other componene and node able to get verified from CA to access each other.
Certificate Signing Request -> have name of the component and its details without sign- ca.csr file

Sign Ceritificate -> It is signed by its own private key(ca.key)

<img width="956" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/c111cbad-ba02-4b84-b508-588597af6c0d">

Here, First private key is generated for the user admin, then public key and then Certificate for the admin user , so that admin have access to the cluster ->admin.csr(file name)
<img width="959" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/b3f885ed-a3b0-42c1-906b-9fbd826bec62">


