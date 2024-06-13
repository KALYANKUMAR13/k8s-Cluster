```
kubectl replace --force -f /tmp/kubectl-edit-1343787734.yaml
```

The above command is used , when there are no manifest availiable in the directory, but pod is created by imperative(through command)
When we want to edit that, we can use this command,

We should edit first, it is not edited, so it will give you a below content, with this we can change it.

A copy of your changes has been stored to "/tmp/kubectl-edit-1343787734.yaml"
error: Edit cancelled, no valid changes were saved.
