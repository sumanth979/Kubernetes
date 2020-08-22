## Working with ReplicaSets
##### To create a new replicaSet.
```bash
kubectl create -f  application.yaml
```

##### To get the details of replicaSet.
```bash
kubectl get replicaset
```
```bash
sample Example:
NAME               DESIRED   CURRENT   READY   AGE
myapp-replicaset   3         3         3       118s
nginx-76df748b9    1         1         1       27h
```
```bash
kubectl get replicaset -o wide
```
```bash
sample Example:
NAME               DESIRED   CURRENT   READY   AGE     CONTAINERS   IMAGES   SELECTOR
myapp-replicaset   3         3         3       2m52s   nginx        nginx    environment=test
nginx-76df748b9    1         1         1       27h     nginx        nginx    pod-template-hash=76df748b9,run=nginx
```

##### To delete the replicaSet.
```bash
kubectl delete replicaset replicaSetName
```

##### To get the more details about the replicaSet.
```bash
kubectl describe replicaset replicaSetName
```

##### To edit/update the exisiting replicaSet.
* Update the application.yaml and run the following command
```bash
kubectl replace -f updatedApplication.yaml
```
* This command will update the template and will recreate the replicaSet
```bash
kubectl edit replicaset replicaSetName
```
* This following command will scale the replicaSet as provided.
```bash
kubectl scale --replicas=6 replicaset replicaSetName
                 (or)
kubectl scale --replicas=6 -f application.yaml               
```

