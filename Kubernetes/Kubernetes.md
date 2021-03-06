# Summary
1. [Install Kubernetes](#Install-Kubernetes)
2. [Pod](#Pod)


## Install Kubernetes

* Open an elevated command prompt
* Run the command 
```
choco install kubernetes-cli
```

* To start the dashboard 

https://www.replex.io/blog/how-to-install-access-and-add-heapster-metrics-to-the-kubernetes-dashboard

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.5.1/aio/deploy/recommended.yaml

kubectl proxy

```

* Set up login credentials

```
kubectl create serviceaccount dashboard-admin-sa

kubectl create clusterrolebinding dashboard-admin-sa --clusterrole=cluster-admin --serviceaccount=default:dashboard-admin-sa

kubectl get secrets

kubectl describe secret dashboard-admin-sa-token-<xxxx>

```

```
eyJhbGciOiJSUzI1NiIsImtpZCI6IkpVU2V4T3h3NTI2R2I1aDBCdW9NT3Y4LXkzUHplMXdHNGV1dzlGQ0s2bFUifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJkZWZhdWx0Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6ImRhc2hib2FyZC1hZG1pbi1zYS10b2tlbi13cm1rcCIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50Lm5hbWUiOiJkYXNoYm9hcmQtYWRtaW4tc2EiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiIxNjZlZDBlMC03ZjVlLTRhOTAtYmNjOS1hYjM2MTQyZmQyZDMiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6ZGVmYXVsdDpkYXNoYm9hcmQtYWRtaW4tc2EifQ.qMPE3mdmys-dbFFG3tOtlvTca8BsQMjzIH1KEHK-KGV0IfJ2oFt2EI2e2eF7N-GcsI9a-YdRfUhK7J3iZb9ClBjUhZZJ2oLUTu4bNteqt6bqyMb33t56prn3fbquGkfRJ9vAkZ-wqWu2jgXNlCU4v1QR0dR1bwNSV20a8sp8GpORWnao4kDfQFtyeavBA4N_V9NYs3CyXe-LeQ23oIa27sx3ZI05dpWlez4bkBA_i7EY-zdB0F3U9DyX7zor0ApDsNWObgcBze6js5VygF0uiOQASPprYRIulvyCW-ml3V2-9XboROCoAJvghqH_m1DUIxUuUgV1JWr_7oqXMISfOg
```

* To access the dashboard navigate to http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/login

* Use the token extracted earlier to login.

* Command to show all pods

```
kubectl get pods
```
* sample command to get a pod running

``` 
kubectl run hello-nginx --image=nginx:alpine --port=8080
```

The pod is running but there is no service which is exposing this pod.

```
kubectl expose pod hello-nginx --type=LoadBalancer --port=8080 --target-port=80
```

## Pod

A Pod is the basic execution unit of a Kubernetes application- the smallest and simplest unit in the Kubernetes obejct model that you create or deploy.

* Pod containers will share the same Network namespace.
* Pod containers have the same loopback netwrok interface.


### kubectl basic

kubectl run [pod-name] --image=nginx:alpine

kubectl get pods

kubectl port-forward [pod-name] <external-port>:<container-port>

kubectl delete pod [pod-name]

### Yaml based deployment

![Event Hub](Images/podyml.jpg)

```yml
apiVersion : v1
kind: pod
metadata :
  name: my-nginx
spec:
  containers:
  - name: my-nginx
    image: nginx:alpine
```
*This is the dry run option for validation*

kubectl create -f nginx.pod.yml --dry-run --validate=true

*The final action command*

kubectl create -f nginx.pod.yml

kubectl apply -f nginx.pod.yml

***If we use apply then it will create or update***

k exec my-nginx -it sh


## Pod Health

Kubernetes uses Probe to check the health of the Pod

There are two types of probes

1. Liveness probes
2. Readiness probes

we can do 

ExecAction
TCPSocketAction
Http probe

The liveness check checks if the container is running or not if not it will restart the container. In case of the 

## Deployments and Replica set

A replica set is the declaritive way to manage the pods. Deployements are on top of replica set.

Deployments and ReplicaSets ensure Pods stay running and can be used to scale Pods.

Role of Replicaset

* self healing mechanism
* Ensure the requested number of Pods are available
* Provide fault tolerance
* Can be used to scale horizontally.
* Relies on Pod template.


Deployment Options:

- Rolling Updates - New one is deployed parallel to the existing ones and old ones are deleted slowly. This is the deault.
- Blue Green deployment
- Canary Deployment
- Rollbacks


**When a browser makes a connection it creates a single connection so it will always connect to the same node**


## Services

A service provides a single point of entry for accessing one or more Pods. 
- Since pods live and die we can not rely on their ip address. That is why we need services to maintain the network. 
- A pod gets it's IP address once they are scheduled so a client will never know the IP before hand.


- The service will abstract the ip.
- Will do the load balancing

![Event Hub](Images/Services.jpg)

### Service types

- Cluster IP
- NodePort
- Load Balancer
- ExternalName



![Event Hub](Images/ServiceTypes.jpg)
![Event Hub](Images/ClusterIP.jpg)
![Event Hub](Images/NodePort.jpg)
![Event Hub](Images/LoadBalancerservice.jpg)
![Event Hub](Images/ExternalNameservice.jpg)

## Create Services

### Structure of a service

![Event Hub](Images/Service_Structure.JPG)

each service gets DNS entry

## Kubernetes Archietcture 

Master node is also called Control Plane Node

![Event Hub](Images/ControlPlaneComponents.JPG)

![Event Hub](Images/NodeComponents.JPG)

![Event Hub](Images/Nodes.JPG)

![Event Hub](Images/NodeNetworking.JPG)

## Path to Kubernetes Repository

https://github.com/kubernetes/kubernetes


kubernetes from apt

