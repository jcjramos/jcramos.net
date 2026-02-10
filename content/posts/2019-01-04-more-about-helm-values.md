+++
title = "More About Helm - Values"
date = 2019-01-04T13:23:10+01:00
draft = false
tags = ["microservices","kubernetes","docker","helm"]
categories = ["microservices"]
+++
Manage deployments is a import concern when creating a microservices based application, given the typical huge number of services involved and the possible variations you need a way to keep complexity under control.
Helm can be a usefull tool, besides been a very cool way to define dependencies ( [see this previous post](../2018-12-19-about-helm/) ),  Helm introduces an interesting concept called values ( not quite original, but implemented in a nice way ). Values allows you to redefine parts your kubernetes yaml (*) files on deployment time, thus allowing more flexibility to your application and, if done right, simplify the deployment. 

Imagine that your application has 2 modes, production and development, this is an obvious candidate to be moved to the values. 

The values.yaml is a standard part of the helm chart and always in the root of the new chart.

In the values.yaml you can define :
```
deployment:
 mode: DEV 
```
Note that the deployment tag is just a way to organize things, you would put all the configurations related to the deployment part under it.

Then in the actual deployment.yaml, that handles the creation of you POD you can add something like :
```
      containers:
		( image & stuff here ) 
		command: [“myInitScript.sh”,” {{ .Values.deployment.mode }}”
```
This way the deployment mode would be passed to your container init script as a parameter, other common way to handle this is to use an environment variable :
```
          env:
          - name: DEPLOYMENT_MODE
            value: {{ .Values.deployment.mode }}
```
when deploying the application you would call :
```
helm install -set deployment.mode=PRODUCTION my-chart.tar.gz
```
And your container would be initialized with :

```
myInitScript.sh PRODUCTION
```

and the DEPLOYMENT_MODE environment variable would be PRODUCTION inside your container. Just change the --set flag to deploy in a different way ! 

(*) YAML are basic kubernetes configuration files, these can be used define Kubernetes Pods, and several artefacts related to a Kubernetes Deployment.
