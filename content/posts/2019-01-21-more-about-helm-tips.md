+++
title = "More About Helm - Tips"
date = 2019-01-21T13:23:10+01:00
draft = false
tags = ["microservices","kubernetes","docker","helm"]
categories = ["microservices"]
+++
Helm is one of the best tools available to simplify your kubernetes development. In this post I’ll be adding some tips that might help you in the development of your helm charts.

Btw, you migth like to see [this previous post](../2018-12-19-about-helm/) and eventually [this one] (../2019-01-04-more-about-helm-values/) 

## Tip 1 – Files in configmaps
There are cases where you will need to move existing configuration files to config maps, a hard working solution is to just type in the whole file with the proper config map indentation.
A more practical solution is to use helm .Files.Glob command. This command will map the content of files in a specific directory to your config map.

Imagine you have 2 xml files, for example defining log4j options – alog.xml and blog.xml in the config directory. 
To map them to a config map you would simply :

```
apiVersion: v1
kind: ConfigMap
metadata:
(metadata here...)
{{ (.Files.Glob "config/*").AsConfig | indent 2 }}
```
And that’s it !

## Tip 2 – Wait for service
Container based services should be resilient and well behaved, thus when service A depends on B, A should handle properly the case B is not available – but not all services are well behaved and sometimes is not praticall to change them. A work around solution is to handle availability  in the heml chart. This can be done using a init container.

```
      initContainers:
      - name: wait-for-service-b
        image: any-basic-image-with-curl-avilable
        command:
         - /bin/sh
         - -c
         - >
           set -x;
           until $(curl --output /dev/null --silent --head --fail service-b-name); do
                sleep 10
           done         
```

In this case the init container would keep “curling” service b until it is available and one then container A would be started.

