+++
title = "Dependency Hell v2019 "
date = 2019-02-04T13:23:10+01:00
draft = false
tags = ["software"]
categories = ["software"]
+++
A recent problem that one of the teams I work with faced, related to a major DB vendor and a set of different incompatible patches remind me of the 90’s. During the late 90’s I’ve worked for a Windows shop that developed a huge DLL based application, taking care of dependencies was a nightmare…early MS win 95 versions didn’t include any good mechanism to track DLL versions, also initially this was not a major concern when developing our application, but we end up creating a lot of DLLs and with additional dependencies from SO and 3rd party DLL’s, so I know fist hand what “DLL hell” means. By the way the term “dependency hell “ is a common software problem that has the honor of it’s own [Wikipedia entry](https://en.wikipedia.org/wiki/Dependency_hell).

> "The dependency issue arises around shared packages or libraries on which several other packages have dependencies but where they depend on different and incompatible versions of the shared packages. If the shared package or library can only be installed in a single version, the user may need to address the problem by obtaining newer or older versions of the dependent packages. This, in turn, may break other dependencies and push the problem to another set of packages."

But with time software systems improved a lot, smart package managers are common these days. A real dependency problem still happens sometimes, software today is much more complex than it was in the late 90’s and any simple 2019 software has a huge dependency tree. But it’s kind of rare in well designed and maintained system. 
But sometimes I’m surprised to find out that today, even large software companies with huge teams don’t tackle the dependency problem right – they seem so unconcern about it like my former team in the late 90’s…they say please apply PATCH A to solve your problem. Then you find that PATCH A that depends on PATCH B that depends on PATCH C that breaks patch A … seems like 1999 all over again ! 



