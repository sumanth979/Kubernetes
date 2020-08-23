## Working with Deployment
Deployment will Handle
* Deployments
* Updates to newer version (Rolling update - without impacting the users) 
* RollBacks to older version 
* Pause / Resume for multiple updates (Pause changes then do the updates one by one and resume changes will effect all changes at once).

##### To create a new deployment with application.yaml file.
```bash
kubectl create -f  application.yaml
            [or]
kubectl apply -f  application.yaml
```

##### To get the details of deployment.
```bash
kubectl get deployment
```
```bash
sample Example:
NAME             READY   UP-TO-DATE   AVAILABLE   AGE
httpd-frontend   0/3     3            0           11s
nginx            1/1     1            1           46h
```
```bash
kubectl get deployment -o wide
```
```bash
sample Example:
NAME             READY   UP-TO-DATE   AVAILABLE   AGE   CONTAINERS       IMAGES             SELECTOR
httpd-frontend   1/3     3            1           33s   httpd-frontend   httpd:2.4-alpine   name=webapp
nginx            1/1     1            1           46h   nginx            nginx              run=nginx
```

##### To delete the deployment.
```bash
kubectl delete deployment deploymentName
```

##### To get the more details about the replicaSet.
```bash
kubectl describe deployment deploymentName
```

