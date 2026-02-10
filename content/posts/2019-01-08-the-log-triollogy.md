+++
title = "The logging triology - ELK Elasticsearch + Logstash + Kibana"
date = 2019-01-08T13:23:10+01:00
draft = false
tags = ["microservices","kubernetes","docker","helm","elk","elastic","kibana"]
categories = ["microservices"]
+++
One of the side effects of a microservices architecture is that checking logs soon becomes a problem. At the beginning of the process, when you think about containerizing an application, it seems simple and straightforward – you just log to stdout and docker or kubernetes handle it. But then ...

## Where is my log ?
The number of different services & service instances rapidly explodes and then it becomes really difficult to find a particular log and to troubleshoot the misbehaviour of a micro-service. The solution is to add a log management application, something to store your logs and to allow you to search through them. 

A nice solution is to use the ELK stack, basically 3 components :

1. Logstash, Collects and transforms 
2. Elasticsearch, Search and Analize
3. Kibana, Vizualize and manage

The ELK deployment in a kubernetes cluster is quite straightforward, definitely the added value it brings worth’s the investment.  

Note1 : As a bonus elastic comes with a REST API that you can use to integrate with your own application.

Note2: [More info here.] (https://www.elastic.co/)