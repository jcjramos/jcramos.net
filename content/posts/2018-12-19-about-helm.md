+++
title = "About Helm"
date = 2018-12-19T13:23:10+01:00
draft = false
tags = ["microservices","kubernetes","docker","helm"]
categories = ["microservices"]
+++
Microservices are supposed to be small and dedicated, the issue when you move an application to a microservices based architecture is that you quickly get many of them. Dealing with each service individually becomes much easier as they get more “micro”, but deal with the whole bunch can be a nightmare.
Look at the example bellow, in the 1st interaction of a typical application it became something like this :

```
+-------------------------+        +-------------------------+
|     typical-frontend    |        |      typical-backend    |
|                         |        |                         |
+-------------------------+        +-------------------------+
                                                              
+-------------------------+        +-------------------------+
|     typical-database    |        |      typical-interf     |
|                         |        |                         |
+-------------------------+        +-------------------------+
```
But then developers became more familiar with microservices, start splitting them in more specialized tasks and it became this : 
```
+-------------------------+        +-------------------------+
|   typical-frontend-A    |        |    typical-backend-A    |
|                         |        |                         |
+-------------------------+        +-------------------------+
                                                              
+-------------------------+        +-------------------------+
|   typical-frontend-B    |        |    typical-backend-B    |
|                         |        |                         |
+-------------------------+        +-------------------------+
                                                              
+-------------------------+        +-------------------------+
|     typical-database    |        |    typical-interf-A     |
|                         |        |                         |
+-------------------------+        +-------------------------+
                                                              
+-------------------------+        +-------------------------+
|     typical-interf-B    |        |    typical-interf-C     |
|                         |        |                         |
+-------------------------+        +-------------------------+
```
Looking at it, you notice that the task to deploy this application is not an easy one, there are many services, it is easy to forget about one of them. Also there are dependencies between the services, how to make sure that an upgrade is made properly ? one way is to use Helm https://helm.sh/
*"Helm helps you manage Kubernetes applications — Helm Charts helps you define, install, and upgrade even the most complex Kubernetes application."*

Definitely worth’s a look, one particular feature that I like is that you can define dependencies, for example you could define something like :
```
requirements.yaml
dependencies:
  - name: typical-frontend-A
    version: 1.2.3
    repository: http://my-repo
  - name: typical-backend-B
    version: 3.2.1
    repository: http://my-repo
etc..

```
and manage the full set of services in a centralized way.

