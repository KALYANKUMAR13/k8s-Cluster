What the user or account can do in the cluster.

1. **Node** : Node Authorizer, this handles the other nodes(worker node) to talk to APi server and their access level is defined
This will check the certificate named **system:node:node01** and authorize it 

2. **ABAC** - Attribute Based Authorization, Associates a single or group of users to associate with the set of permissions. Policy should be added to each user

3. **RBAC** - Role Based Access Control, here Role is created for developer and associate with the particular user

4. **Webhook** - Out source the authorization mechanism, Open Policy Agent is the 3rd party tool for organising the authorization.

AlwaysAllow - Allows All requests - By default , this is one is present . ,, We can set above 4 things in the always allow section

AlwaysDeny - Denies all requests.
