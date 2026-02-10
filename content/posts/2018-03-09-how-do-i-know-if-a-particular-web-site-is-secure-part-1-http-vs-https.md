---
layout: post
title: How do I know if a particular Web site is secure ? HTTP vs HTTPs
date: 2018-03-09T13:23:10+01:00
author: jcarlosr
comments: true
categories: [tips, vulnerabilities]
---
<span style="font-weight: 400;">The short answer is you don’t know … there is no simple ways to check, web infrastructure these days is complex and there is no public reporting of security practices used or even testing reports. The web owner can ( and will if they care about security ) use some kind of vulnerability testing, but it’s actually not nice to test 3rd party sites for vulnerabilities and generally people don’t make these public.</span>

<span style="font-weight: 400;">Anyway there are some things you can check, these will give you at least some guidelines if the people maintaining the particular service care at least a little bit about security.</span>

<span style="font-weight: 400;">The site uses HTTP instead of HTTPS ?   runway then … you can check this is the browser as a HTTPS site is typically marked as secure, some browsers present it as a padlock icon.  If the padlock doesn't show up it means HTTP is used, the connection is not encrypted and there are a lot of potential issues with that site. </span>

<span style="font-weight: 400;">A basic issue is that as information is not encrypted the packages traveling back and forward can be sniffed and any  information that you provide is basically public. </span><span style="font-size: 1rem;">You can also be victim of a “sniffing” attack, typically the target of this attack is the user web browser is relatively simple to mount on a public unencrypted WIFI network when you use HTTPs.  Traffic is visible and a attacker can modify it and do something with your browser.</span>

<span style="font-weight: 400;">Thus something very simple like that tells your browser to display "hello world": </span>

<em><span style="font-weight: 400;">&lt;</span><span style="font-weight: 400;">html</span><span style="font-weight: 400;">&gt;</span><span style="font-weight: 400;">
</span> <span style="font-weight: 400;">&lt;</span><span style="font-weight: 400;">body</span><span style="font-weight: 400;">&gt;</span><span style="font-weight: 400;">
</span> <span style="font-weight: 400;">Hello world</span><span style="font-weight: 400;">
</span> <span style="font-weight: 400;">&lt;/</span><span style="font-weight: 400;">body</span><span style="font-weight: 400;">&gt;</span><span style="font-weight: 400;">
</span> <span style="font-weight: 400;">&lt;/</span><span style="font-weight: 400;">html</span><span style="font-weight: 400;">&gt;</span></em>

<span style="font-weight: 400;">Might became :</span>

<em><span style="font-weight: 400;">&lt;</span><span style="font-weight: 400;">html</span><span style="font-weight: 400;">&gt;</span><span style="font-weight: 400;">
</span> <span style="font-weight: 400;">&lt;</span><span style="font-weight: 400;">body</span><span style="font-weight: 400;">&gt;</span><span style="font-weight: 400;">
</span> <span style="font-weight: 400;">Hello world</span><span style="font-weight: 400;">
</span> <span style="font-weight: 400;">&lt;script&gt;some hidden bitcoin mining code here :-)</span></em><em><span style="font-weight: 400;">&lt;/script&gt;</span></em>

<em><span style="font-weight: 400;">&lt;/</span><span style="font-weight: 400;">body</span><span style="font-weight: 400;">&gt;</span><span style="font-weight: 400;">
</span><span style="font-weight: 400;">&lt;/</span><span style="font-weight: 400;">html</span><span style="font-weight: 400;">&gt;</span></em>

<span style="font-weight: 400;">There are also a lot of known vulnerabilities with WIFI, thus using HTTP in an encrypted WIFI network is not much better. </span>

<span style="font-weight: 400;">Other problem is </span><span style="font-weight: 400;">spoofing; for example you click a link to my.bank.com that is actually a link to  fake.bank.com that misleads you to provide your user name and password.</span>

<span style="font-weight: 400;">HTTP is definitely not ok for any site that requires you to provide some information, like user name or passwords. For more simple sites that only require browsing, like a blog, use with moderation. </span>

<span style="font-weight: 400;">Btw: If you would like to know more about HTTPS check this wonderful <a href="https://medium.freecodecamp.org/https-explained-with-carrier-pigeons-7029d2193351">article about HTTPS and carrier pigeons by Andrea Zanin</a>. </span>
