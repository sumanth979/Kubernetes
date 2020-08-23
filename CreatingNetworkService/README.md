## Working with Network Services
##### To create a new service.
```bash
kubectl create -f  service.yaml
         [or]
kubectl apply -f service.yaml
```

##### To get the details of service.
```bash
kubectl get services
```
```bash
Sample Output:
NAME            TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
kubernetes      ClusterIP   10.96.0.1       <none>        443/TCP        2d4h
myapp-service   NodePort    10.101.161.22   <none>        80:30004/TCP   11s
```
```bash
kubectl get services -o wide
```
```bash
Sample Output:
NAME            TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE     SELECTOR
kubernetes      ClusterIP   10.96.0.1       <none>        443/TCP        2d4h    <none>
myapp-service   NodePort    10.101.161.22   <none>        80:30004/TCP   8m24s   app=myapp
```
