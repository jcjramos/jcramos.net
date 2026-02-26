---
layout: post
title: "The Night I Learned to Dogfood: A Lesson from Nokia's Ops Center"
date: 2026-02-26T13:23:10+01:00
author: jcramos
comments: true
tags: ["dogfood","nokia","software"]
categories: ["software"]
---
Dogfooding—the act of using your own product—is a simple, foundational principle in software development. But the most valuable lessons in dogfooding aren't learned during a daytime demo. They’re learned when your system breaks and you have to truly live with the consequences.
This takes me back to 2010, when I was at Nokia working on a crucial telco monitoring system.

### The Phantom Failure at 2 AM
The system was running, but a peculiar and frustrating issue kept cropping up: the operator was complaining about consistent failures every day at approximately 2 AM. We couldn't track the problem through our usual diagnostic tools, which left us baffled. 
This is a common failure mode in software: a problem that is simple on the surface but impossible to replicate in a testing environment because it only exists in the wild, interacting with the real world's strange physics and operational schedules.
With no clear path forward, I ended up deciding to spend the night in the Ops Center to try and figure it out. I recall that my colleagues were hesitant about this kind of commitment, but I took the opportunity. Sometimes, to truly solve a bug, you have to become a co-operator. You have to remove the abstraction layer between the developer and the user experience.
### The Real Root Cause
After a long night observing the system in its natural habitat, the root cause was discovered: there were a lot of scheduled maintenance operations happening around 2 AM because the network load was lowest at that time. Our monitoring system wasn't failing; it was faithfully reporting on the system state, which included the intentional downtime of various components during maintenance. Our software, quite literally, couldn't handle the reality of the environment it was deployed in.
But finding the root cause—a problem of coordination and timing, not a logical bug—was the minor victory.

### The Major Gain
The actual major gain was what came next: I learned a lot about how the software was actually used. Sitting there, watching the operators, I saw firsthand the friction points, the missing features, and the moments when the user's intent clashed with the software’s design. 
This experience fundamentally changed how I approached my work, transforming me into a better developer and leading to major contributions to the system.
This story connects back to what I wrote in [From Nokia’s Sprints to the AI Swarm](../2026-02-20-from-nokia-sprints-to-ai-swarn). While we often focused on formal frameworks like Scrum at Nokia, that night in the Ops Center was the ultimate lesson in the spirit of Agility: continuous feedback and prioritizing technical excellence by experiencing the system yourself. It was a commitment to accountability, a principle that remains crucial in the age of AI.

AI agents can write the code, but they can’t dogfood it in the way a human engineer can—they can’t sit in the Ops Center and see the frustration in the operator’s eyes. We may be moving toward Intent-Based Development, where AI handles the how, but we still need human engineers to define the what based on a deep, experiential understanding of the product’s reality. That human insight and accountability remains our most essential contribution.
