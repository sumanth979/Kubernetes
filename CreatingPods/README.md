# Creating POD with yaml file

##### To create a pod with yaml file.
```bash
kubectl create -f application.yaml 
        (or)
kubectl apply -f application.yaml
```

##### To get the more details about the POD.
```bash
kubectl describe pod podName
```

##### To delete the running POD
```bash
kubectl delete pod podName
```

##### To edit and rebuild the running POD
* This command will update the template and will recreate the POD
```bash
kubectl edit pod podName
```
