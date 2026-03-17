---
layout: post
title: "The Saturday Sprint: Building a Book Tracker with AI"
date: 2026-03-17T13:23:10+01:00
author: jcramos
comments: true
tags: ["software","ai"]
categories: ["ai"]
---

I have a common problem: I own too many books (both physical and on my Kobo) and a terrible memory for which ones I’ve actually finished. To fix this, I decided to build a simple tracking web app.
Usually, a full-stack project—even a "simple" one—is a week-long commitment. I used this as a benchmark to see how far I could push AI as a coding partner. I managed to go from zero to a deployed PostgreSQL/React app in a single Saturday afternoon.

### The Tech Stack
- Frontend: React / JavaScript
- Backend: Node.js
- Database: PostgreSQL
- The "Engine": Claude (Anthropic) & Gemini (Google) 

### The Efficiency Gain
The most striking part of this experiment wasn't just the code generation; it was the context management. Modern AI's ability to stay "in the room" with me through the debugging phase was impressive.
Tasks that would have taken 5–7 days of sporadic evening work were compressed into about 5 hours. We’re talking a 10x to 20x efficiency gain for straightforward, "from-scratch" builds.

### Where AI Hits a Wall: Deployment
While the AI can write a perfect React component in seconds, deployment remains the final boss. Connecting the app to the database and navigating environment-specific errors was the hardest part. I ended up feeding raw log outputs back into the AI to troubleshoot. It handled the bug fixes well, but it reminded me that you still need to know what to ask and where to look.

### Is AI Taking the "Fun" Out of Dev?
There’s a common argument that AI-generated code kills the joy of programming. I disagree.
For me, the "fun" isn't in the syntax or the boilerplate—it's in the architecture, the features, and seeing a tool actually work in the real world. Using an LLM feels like driving a high-performance sports car:
- It’s incredibly fast.
- It’s a "dangerous tool" if you don't know how to drive.
- If you lack experience, you’ll likely just generate a high volume of unmaintainable, subpar code.
  
### Quality > Volume
I’m skeptical of companies boasting that "90% of our code is AI-generated." Productivity isn't measured in lines of code; in fact, the goal should be the minimum amount of code necessary to keep things maintainable. AI tends to be wordy. The human's job is now to be the editor—trimming the fat to ensure the app remains readable six months from now.

### What’s Next?
The "crude" version is live, but I want to automate the data entry. The next feature: taking a photo of my physical bookshelf and having an AI vision model parse the titles directly into the database.
