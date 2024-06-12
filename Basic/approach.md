

The commands we are using now is imperative method. The **imperative method** tells each and every thing in the file. 

```
kubectl run my-pod --image=my-image
kubectl create deployment my-deployment --image=my-image
kubectl expose deployment my-deployment --port=80 --target-port=8080
kubectl create configmap my-config --from-literal=key1=value1 --from-literal=key2=value2
kubectl edit deployment
```

Declarative method:
The declartive method can says the final destinaion. Hers, it looks upon the file and make the changes.

```
kubectl apply -f manifest.yaml
```

Update the manifest:

```
kubectl edit deployment myapp.yaml
```
The above command will not save the edited content in the original manifest, But change is happend in the cluster.


```
vi myapp.yaml
kubectl replace -f myapp.yaml
kubectl apply -f myapp.yaml
```
This command is will will change the content in the maifest and cluster deployment is modified.
