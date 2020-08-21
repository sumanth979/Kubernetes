# Kubectl

##### To get the kubectl version
```bash
kubectl version (or) kubectl version --client
```

## Working with Nodes
##### To get the running Nodes
```bash
kubectl get nodes
```
##### To get the running Nodes with extended details
```bash
kubectl get nodes -o wide
```

## Working with PODs
##### To get the running PODs
```bash
kubectl get pods
```

##### To get the running PODs with more details (like ipadd of POD, Node in which POD is running.. etc)
```bash
kubectl get pods -o wide
```

##### To create a new POD with running an application image.
```bash
kubectl run applicationName --image=imageNameInDockerRepository
```

##### To get the more details about the POD.
```bash
kubectl describe pod podName
```
