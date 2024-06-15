Who can access the cluster ->service accounts
What can they do in cluster ->RBAC

Authentication(basic):
Auth mechansims -> static password file, static token file, certificates and Identity Providers like LDAP

In a csv file, write users and password and attach to kubeapi server(in command in the manifest)
token file is similar to csv file
This is the basic auth(! recommended one), we need to request the api server in below image format
Username and password based authentication(Deprecated from v1.19)
<img width="782" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/be02cffb-3937-4198-ad11-97f714778ef0">
Token authentication
<img width="955" alt="image" src="https://github.com/KALYANKUMAR13/k8s-Cluster/assets/35223898/17da3267-8852-4961-8b4d-232cd3f80058">





