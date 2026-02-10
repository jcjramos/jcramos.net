+++
title = "Developing Secure Applications"
date = 2018-11-19T13:23:10+01:00
draft = false
tags = ["security","testing"]
categories = ["security"]
+++
Everyday there is a new story about a hacking incident somewhere, developing secure applications is definitely one of the most important challenges in the software world.

<img src="https://upload.wikimedia.org/wikipedia/commons/9/94/Almourol_034.jpg"
     alt="Almourol Castle in Portugal"  width="350"/>
	 
A good analogy is the defence of a castle, in the medieval world castles were very important. In a anarchic world with many threads  they were the centres of power and stability. But how to defend a castle from your enemy’s ? a well built castle in a high point was a clear advantage, will a relatively small force it could be defended against a much powerful enemy.
But as a defended you had to make sure that you didn’t miss any spot, the enemy would look for weak points and you would have to make sure that you had none. Defences must be built and then continuously maintained and updated.

Modern day software developers face similar challenges, you have to make sure that you get everything right, you cannot miss a spot or you are doomed.
The issue is that over the years software has been growing more complex, as our minds are limited we keep adding layers and layers of abstraction to try to keep things simple and keep productivity up. Result is that an application in 2018 might look like the castle bellow:


```
+----------------+                                            +-------------+
|                |                                            |             |
| Web Interfaces |                                            | Source Code |
|                |                                            |             |
+-------------------------------------------------------------+-------------+
|                |                                                          |
|    Docker      |               Application Containers                     |
|                |                                                          |
+---------------------------------+-----------------+-----------------------+
|                                 |                 |                       |
|    Virtualization Platform      |   Kubernetes    |  Container image OS   |
|                                 |                 |                       |
+---------------------------------------------------------------------------+
|                                 |                 |                       |
|            Hardware             |                 |         VM OS         |
|                                 |                 |                       |
+---------------------------------+                 +-----------------------+
```

The result is that your Castle is huge and you still have to make sure you have no weak spots, some strategy’s :

- Keep a mechanism to update your 3rd party components; make sure security patches are installed.
- Pay particular attention to important components like OS
- Make sure there are no default passwords used anyware
- Use automated testing tools, test the infrastructure OS and the container images for known vulnerabilities, also test the web interface ( many security testing tools are costly, but they worth their price if they can help to keep your system secure )
- Make sure your source code is secure, free tools like Sonar can help you to check. 

