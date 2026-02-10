+++
title = "Telco Software : Virtualization vs Cloudification"
date = 2018-12-18T13:23:10+01:00
draft = false
tags = ["virtualization","cloud","aws"]
categories = ["telco"]
+++

Today I came across this very interesting article on [The Economist]( https://www.economist.com/business/2017/04/12/cloudification-will-mean-upheaval-in-telecoms ) regarding “Cloudification will mean upheaval in telecoms”, it’s kind of “old news” but make me think about the current trends in telco software development.
From my experience telco industry was fast to virtualize but slot to cloudify. Virtualization and cloudification are often used with the same meaning but they are actually different concepts. Virtualization is mostly related to the optimization of hardware resources, running more software on a given amount of physical infrastructure. Cloud computing is  a metaphor for a system that is based on a shared pool of configurable computer resources that can be provisioned over the internet, typically with minimal effort - public cloud services like Amazon AWS are highly automated, elastic/scalable and pay-as-you-go ( you just need a credit card ). Cloud computing makes use of virtualization to enable the elasticity and achieve economies of scale.
For many years telco operators have been using virtualized solutions at the core of their networks, virtualization is expanding to more and network functions, in particular at the edge of the network.

Regarding cloud the adaptation has been much slower, one of the issues is the latency,  many telco functions need low latency that require that the services are located “near” their consumers. Other challenge is the data, telcos deal with sensitive data, data protection requirements and national laws often mandate that telco data must be stored in a specific country, thus use a generic cloud is sometimes difficult. Adding to this there are the many legacy systems that are difficult to evolve to a cloud architecture and the mindset, in particular the perception of a loss of control. 

But now there powerful trends that are making most telco operators to rethink their cloudification approach, in my opinion the most important is the 5G adoption. 5G leads to a network element explosion and a data explosion, this means extra costs and much more computing power ( virtualized or not ). To maintain the costs bearable telco systems will have to make use of efficient and cost effective cloud solutions, at least for same part of their systems.
