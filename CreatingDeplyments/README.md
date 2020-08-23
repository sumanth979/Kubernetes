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

## Updates and RollBacks
### Rollout and Versioning
* When a deployment is created it triggers a new Rollout
  * A new Rollout will create a new deployment Revision. (versioning - Revision 1)
* In future when the application is upgraded (container version upgraded etc..) it will trigger a new Rollout
  * A new Rollout will create a new deployment Revision. (versioning - Revision 2)
* This help us to keep track of changes made to our deployments and enables us to rollback to a previous version when ever necessary.

##### To check the status of deployment rollout
```bash
kubectl rollout status deployment/deploymentName
```

##### To check the status of rollout history of a deployment
* It will provide the
  * Revisions and
  * History of deployment
```bash
kubectl rollout history deployment/deploymentName
```

## Deployment Strategies
#### Recreate Strategy
* In this strategy we will delete all the running instances and will create the instances again with the newer updates.
  * **Disadvantage:** The application will be down for some time.(The time gap after shutting down all the instances and the new instances become ready)

#### Rolling Update Strategy
* In this strategy we will delete one running instance and will create the one instances again with the newer updates one by one.
* Default deployment Strategy
  * **Advantages:** No application downtime & seemless upgrade.


##### To update deployment
```bash
kubectl apply -f updatedApplication.yaml
```

##### To update the image in deployment
```bash
kubectl set image deployment/deploymentName imageName=newImageName.
```

