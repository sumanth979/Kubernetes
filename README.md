# Kubernetes

#### Setting up kubernetes
##### Installing Minikube
```bash
https://kubernetes.io/docs/tasks/tools/install-minikube/
```
##### Installing kubectl
```bash
https://kubernetes.io/docs/tasks/tools/install-kubectl/
```

## Working with Minikube
##### Start the Minikube using virtualbox driver.
```bash
minikube start --driver=virtualbox
```

##### To check the status of the minikube
```bash
minikube status
```

##### To stop the running minikube
```bash
minikube stop
```

##### To cleanup the local state of minikube
```bash
minikube delete
```

##### To get the url of service in minikube
```bash
minikube service serviceName --url
```

#### To know more details about Kubectl
* [Kubectl](https://github.com/sumanth979/Kubernetes/blob/master/WorkingWithKubectl.md)
