+++
title = "Docker in 6 minutes"
date = 2020-01-27T13:23:10+01:00
draft = false
tags = ["software","docker"]
categories = ["microservices"]
+++

## Trying to make some sense  of docker for non-technical people.

Do you think it is more expensive to send a container full of goods from Lisbon to China or a plane ticket that allows one of you to go to from Lisbon to China? Actually it is roughly the same, the prices vary but on average the costs are around 1200 €.

It is surprising that it is relatively cheap to transport such a huge container full of goods. More surprising to think that  despite all our innovations in transport, the item that really enabled globalization and allows to have todays supermarkets full of things from around the world at relatively low prices is a humble standard metal box more or less with 13mx3mx3m which allowed to lower transport costs in such a way that our supermarkets can full of products from all over the world at relatively low prices - to get an idea the cost of transport weighs on average less than 1% in the final cost of a product.

Containers are a good analogy for a small revolution that we have seen in the Software industry in recent years.

Let me tell you a story, imagine BeBola (1): a small startup that sells “Bolas de  Berlin” (2). Like any company in the 21st century they decide to create a website that allows customers to place orders.

The site like any software service must run on a computer somewhere, Bebola's first approach is to buy a server and connect it at the office.

They soon realize that this is not a very good idea, on the one hand the electricity consumption is high, one day the cleaning lady disconnects the cable from the computer to connect a vacuum cleaner and the site is down. No orders that day.

Bebola people decide that it is better to hire a hosting service, but they soon realize that they also have their problems. On the one hand, the costs are high, in the meantime the summer arrives and everyone likes to eat “bolas de berlim” on the beach, there are so many accesses that the site is constantly down, no orders again during the peak season ! 

Meanwhile at Bebola they heard about a new technique called virtualization, in which virtual machines are used to simulate physical environments. These can be contracted from cloud services like AWS with friendly costs (because the hardware is shared), with the advantage that they are relatively easy to scale; Bebola's website changes to AWS, now during the summer they rent more servers and everything works.

But, to allow several server instances the software got more complex. Additionally they added much more functionality and maintenance starts to be a problem. Complexity grows not only in the site itself but also with integrations with payment systems, a mobile version, there are also recurring security problems in operating systems that want constant updates.

The favorite excuse of software developers was common in Bebola those days - the famous phrase that even those who are not connected to the software must have heard  somewhere “it works on my machine”. In reality the differences between the development environment and the end brought constant problems in the updates.

What was the solution? at Bebola they heard about Docker and decided to give it a try. They splited the functionalty in containers acording to the micro services architecture. Each container included the necessary software to perform is function on the website, but also with the dependencies and configurations necessary to run. This way it that can be moved quickly between development and production environments without side effects. In addition, the micro-service architecture required to use Docker makes integrations with other services such as payment systems much simpler.
Other advantage is that containers tend to be small, at least smaller than virtual machines as they only package the libraries that are necessary for them to run.  Thus the costs are lower in cloud environments where costs tend to be related to the size of the deployment.

Briefly, a container is a way to package a software service and all its libraries and other facilities in an easy way to transport. Docker is a technology that allows you to create, store and distribute applications in containers - in the same way that a physical dock is optimized to move containers from one side to the other.

In the shipbuilding industry, before the introduction of standardized containers a ship took on average 2 weeks to navigate from New York to Lisbon and then 2 weeks to load / unload . Today a super container carrier needs only a few hours in the most efficient ports. The expectation is that the use of Docker and containers will bring efficiency gains similar to the software industry.

*Note : If you are curious about how physical containers changes the global commerce ecosystem check [this documentary on the BBC] (https://www.bbc.co.uk/programmes/p04g1ddh).* 


*(1) Imaginary name* 

*(2) [Bolas de Berlin](https://pt.wikipedia.org/wiki/Bola_de_berlim) is a Kind of a Doughnut, the   Portuguese version of a Berliner very popular in beaches during the summer.* 


