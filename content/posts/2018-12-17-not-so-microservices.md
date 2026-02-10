+++
title = "About not-so-microservices"
date = 2018-12-17T13:23:10+01:00
draft = false
tags = ["microservices","kubernetes","docker","architecture"]
categories = ["microservices"]
+++

Sometimes, in particular when moving large legacy systems to a microservices architecture you came up with the dilemma, what to do about the not-so-microservices ? these are typically large monolith blocks from a bygone era. Developers are afraid of these, no one want’s to mess with them. But we live in a messy world with lot’s of IT infrastructure relying on old code – it is not possible to rewrite all the old code in a “container friendly” way.
Thus what to do when you have to deal with a large service, that doesn’t seem to fit well on a microservices architecture ? 
My view is that, generally the best option is to containerize it anyway – likely you will end up with a very large container, but docker architecture and existing tools are flexible enough to handle most common challenges.
In the end you’ll end up with a far from ideal system, but at least it will be a system where all the services are managed in a consistent way. The alternative, to have a part of the system outside the Kubernetes containerized platform is likely much worse in the long term. 
