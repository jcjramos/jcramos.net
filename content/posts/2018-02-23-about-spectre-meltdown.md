---
layout: post
title: About Spectre & Meltdown
date: 2018-02-24T13:23:10+01:00
author: jcarlosr
comments: true
tags: ["security",vulnerabilities"]
categories: ["security"]
---
<span style="font-weight: 400;">For several reasons Meltdown and Spectre are a very interesting set of vulnerabilities that illustrates well the challenges involved to create secure software applications these days.</span>

<span style="font-weight: 400;">Details &amp; more info in :</span>

<a href="https://meltdownattack.com/"><span style="font-weight: 400;">https://meltdownattack.com/</span></a>

<span style="font-weight: 400;">Some semi random thoughts about it : </span>
<ul>
 	<li style="list-style-type: none;">
<ul>
 	<li style="font-weight: 400;"><span style="font-weight: 400;">Although not so risky as been portrayed in the press, basically both vulnerabilities are related to isolation - means that a potential attacker can use them to get information on the local computing device, not to attack remote systems. But note that “local” these days might be a remote data center hosting many different services through virtualization/containerization.  </span></li>
 	<li style="font-weight: 400;"><span style="font-weight: 400;">The part that it is basically a hardware problem will make it incredibly difficult to patch, thus we can expect Spectre &amp; Meltdown to be around for many years. Just remember WannaCry, making use of a vulnerability patched months before, spread during  May 2017 affecting important organizations like the UK National Health Service that did not have their systems properly updated.</span></li>
 	<li style="font-weight: 400;"><span style="font-weight: 400;">When developing software it is generally a good idea to minimize optimizations, when you optimize computer code it usually becomes for difficult to read and complex - increased complexity brings potential errors and security issues.  Speculative execution in processors is basically an optimization and the “root cause” for meltdown.</span></li>
 	<li style="font-weight: 400;"><b><span style="font-weight: 400;">Existing generation of Anti-virus software is basically useless against potential exploits, this shows the limitations of existing protection tools. Hopefully AI evolution will bring a new generation of more effective Anti-virus software in the near feature, current generation looks more like a “<a href="https://en.wikipedia.org/wiki/Cargo_cult">cargo cult</a>”.</span></b></li>
</ul>
</li>
</ul>
&nbsp;

&nbsp;
