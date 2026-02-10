+++
title = "The Ingress triology"
date = 2018-12-14T13:23:10+01:00
draft = false
tags = ["microservices","kubernetes","docker","ingress"]
categories = ["microservices"]
+++

Deploying http services in a Kubernetes cluster can be a bit challenging, although the basic principles are simple it is not always easy to manage all the details.  Docker & Kubernetes were designed with isolation in mind  ( they are called containers for a reason ).
You need to understand the Ingress triology properlly : 
Ingress -> Service -> Containers.

The Container
-------------
The fist step is to have the container running, inside the container there is a service running that accepts HTTP connections – let’s say tomcat running a webserver.
The tricky part is that it is not enough to have the service running inside the container.
Imagine that you ssh to the container and check the service, lile 
```
[container bash]wget http://localhost:8080 [OK)
```
But then you come outside the container :
```
[kube bash]wget http://container.ip:8080 [NOK)
```
That’s because it must be specified that the port is to be exposed outside.
In your yaml/helm chart deployement you need something like :
Now you need to specify 

```
metadata:
  name: my-very-nice-container
…
          ports:
            - containerPort: 8080
              name: http
```
Now, when the POD with the container is deployed you can do something like :
```
[kube bash]wget http://container.ip:8080 [OK)
```

The Service
-------------
In the previous step you already deployed a container with your service and it works ! now the issue is that the container IP might change, or your are deploying in a cluster and you don’t know in what node it will run. The proper way to handle this is to create a service.

```
metadata:
  name: my-very-nice-service
...
    spec:
      containers:
      - name: my-very-nice-container
        ports:
        - containerPort: 8080
```

And that’s it, now you can refer to the service by it’s name, regardless of the node, like :
```
[kube bash]wget http:// my-very-nice-service:8080 [OK)
```
The Ingress
-------------
In the previous part we already have a kubernetes service defined and can use it inside the cluster, but what about access from outside the cluster ? then you need an ingress, and ingress will enable the system to forward outside requests to your service.
In the bellow example we state that requests to my.very.nice.host.com/very-nice will be forwarded to the service defined in the previous step.

```
metadata:
  name: my-very-nice-ingress
...
spec:
  rules:
  - host: my.very.nice.host.com
    http:
      paths:
      - path: /very-nice        
        backend:
          serviceName: my-very-nice-service
          servicePort: 8080
```
```
[outside bash]wget http://my.very.nice.host.com//very-nice [OK)
```
