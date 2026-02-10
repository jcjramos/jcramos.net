---
layout: post
title: DST and Software
date: 2018-03-26T13:23:10+01:00
author: jcarlosr
comments: true
categories: [DST, Software]
---
Last weekend was a 47 hour oddity; across Europe it is like this every last weekend of March due to the annual DST change to “Summer Hour”. It is annoying but I know if could be worse, at least these changes are unified and regulated, thus all the counties that are part of the EU "unified clock regime" make the change in the same day.

These changes tend to remind me of years ago when I’ve worked in a software that processed Television audiences, what to do with the GAP when the clock jumps from SAT 1:00 AM to SAT 2:00 AM ? in our case we have decided to “duplicate” the 0:00 to 1:00 period, but a dedicated routine was written in C++ to handle it. Not actually an easy task…jumping time doesn’t make life easy for software developers, in particular if the software somehow relates to continuous time related data.

These time zone changes don’t seem of much use and actually create a lot of minor problems – my Phone knows how to automatically update DST, but not my analog clock, thus I had to tour around the house last Saturday and check what clocks need to be updated and not ( end up missing the car clock…) , also the dog hatted to walk so early this morning. Although I really like the long daylight in summer days I think we would all gain without this unnecessary annoyance.

What is different this time, is that like me a lot of people think that this is unnecessary and there is even a recommendation to <a href="https://www.timeanddate.com/news/time/eu-parliament-abolish-dst.html">re-evaluate the DST in Europe</a>.

But if DST is scrapped this means that all the Software that knows how to automatically adjust time must be updated, how that will be managed ? after some digging I’ve noticed that time zone changes are actually not that rare in the world – for example Turkey changed in 2015, and Microsoft has a specific team that handles time zone related issues named <a href="https://www.wired.com/story/microsoft-time-lords/">the “Time Lords”</a>.

I wonder how many windows updates are related to some country around the world changing clocks.

Note: <a href="https://en.wikipedia.org/wiki/Leap_second">Leap Seconds</a> are even stranger that DST … hours like 23:59:60 are difficult event for Humans to understand 😊

&nbsp;

Btw: I wonder what the people who designed the way we count the time had in mind ? let’s divide the day in 24 pieces because err … we have 10+10 fingers but 12+12 is way cooler, and them we divide it in 60 smaller bits because err !?!?! and then 60 again, but then we divide by 1000 because it makes sense. 
Funny, for some time the French used something called “Decimal Time “ https://en.wikipedia.org/wiki/Decimal_time
