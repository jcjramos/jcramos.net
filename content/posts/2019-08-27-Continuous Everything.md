+++
title = "Continuous Everything"
date = 2019-08-27T13:23:10+01:00
draft = false
tags = ["software","cicd","java"]
categories = ["software"]
+++
I’ve found out this week that the famous [Joel test](https://www.joelonsoftware.com/2000/08/09/the-joel-test-12-steps-to-better-code/) reached 19 years of age this month, besides reminding me how old I’m getting  it reminded me of the importance of proper CI/CD - [Continuous Integration] (https://en.wikipedia.org/wiki/Continuous_integration) / [Continuous Delivery] (https://en.wikipedia.org/wiki/Continuous_delivery) pipelines in software development. 

At the time I’ve came across “Joel Test”, found that comply with rule number 2 migth be a good thing and I’ve tried to create a simple build script that would emulate a kind of basic CI pipe – at the time I was working on a application composed of a set of components based on Win32 DLL’s+EXE; my CI script would compile the necessary DLL’s, join them in a directory and check if it run. Seems and it’s quite basic but it was really helpful, you would be surprised by how many times things got messed up, [Dependency_hell](https://en.wikipedia.org/wiki/Dependency_hell) Someone ? , I was convinced how valuable was this early feedback tool, thus have been a fan of CI/CD for the rest and most part of my professional live.

Meanwhile I’ve been involved in larger and more complex projects, when you have a large team the ability to do an early validation on any software change becomes a must have necessity. A fully functional CI, meaning something that ensures the integrity of every code checked in in the system ensures that people are working in sync.
Then comes the CD part, and this has different meanings to different people – my view is that at least it should involve installing the software in a staging internal system that is similar to the target one. Automated tests should be run against this system and ensure the software use cases are covered.

On a really well tuned CI/CD it could actually be used for automated delivery to final costumers, assuming that automated tests really ensure the quality, that costumers desire it and there are no other limitations – for example if your contract requires a 99.9% uptime you might want to limit upgrades and have someone looking when they happened.

Although the tools involved in the creation of CI/CD pipelines, the reality is that a suitable pipeline and a the related automated tests require a lot of effort and investment. Besides the more obvious tools to manage the actual pipeline,  like Jenkins+Git/Gerrit, Bitbucket or GitLab there’s the actual build, the unit tests, the deployment & installation, the setup of the target system, the tools for automated tests that can include a set of scripts and web test tools like Selenium. 
These days on of the important aspects of testing is also security, you need to ensure that your software is deployed without known security vulnerabilities – the best way is to integrate security vulnerability check in your CI/CD pipeline, a tool like Sonar can check code vulnerabilities, tools like Nexus can be automated to check a installed target system and more recently to Docker containers.   In the end the CI/CD system itself will end to be something almost quite as complex as the software it produces … but my experience is that it worth’s the investment. 

A tipical CI/CD in the Java world today looks like this :

```
+-------------------------+         +-------------------------+          +-------------------------+        +-------------------------+                            
|                         |         |                         |          |                         |        |                         |                            
| Compile Java code       |         |                         |          |                         |        |                         |                            
| Run Unit Tests          |         |  Build Container and    |          |  Validate container     |        |   Publish container     |                            
| Check Secure code       |---------|  generate helm chart    |-----------  Check docker vulnerab. |--------|   and chart             |                            
| Create & Publish JAR    |         |                         |          |  Check Helm chart       |        |                         |                            
| Artifact                |         |                         |          |                         |        |                         |                            
|                         |         |                         |          |                         |        |                         |                            
+-------------------------+         +-------------------------+          +-------------------------+        +-------------------------+                            
                                                                                                                                                                   
                                                                                                                                                                   
                                                                                                                                                                   
 +-------------------------+        +-------------------------+          +-------------------------+        +-------------------------+                            
 |                         |        |                         |          |                         |        |                         |                            
 |                         |        |                         |          |                         |        |  Publish to valid       |                            
 |  Prepare Staging        |        |   Deploy containers     |          |  Run Automated Tests    |        |  Releases               |                            
 |  Lab                    |---------   to Stagin Lab         |-----------       ( Smoke )         |--------|                         |                            
 |                         |        |                         |          |                         |        |                         |                            
 |                         |        |                         |          |                         |        |                         |                            
 |                         |        |                         |          |                         |        |                         |                            
 +-------------------------+        +-------------------------+          +-------------------------+        +-------------------------+                            
                                                                                                                                                                   
                                                                                                                                                                   
 +-------------------------+        +-------------------------+          +-------------------------+        +-------------------------+                            
 |                         |        |                         |          |                         |        |                         |                            
 |                         |        |                         |          |                         |        |                         |                            
 |  Prepare Security       |        |   Deploy containers     |          |  Run Security Test      |        |   Publish release       |                            
 |  Staging Lab            |--------|   to Stagin Lab         | ---------|  Vulnerability          |---------                         |                            
 |                         |        |                         |          |                         |        |                         |                            
 |                         |        |                         |          |                         |        |                         |                            
 |                         |        |                         |          |                         |        |                         |                            
 +-------------------------+        +-------------------------+          +-------------------------+        +-------------------------+  
```