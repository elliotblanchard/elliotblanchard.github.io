---
layout: post
title:      "Collab Visuals: Create Together"
date:       2020-10-22 21:51:26 -0400
permalink:  collab_visuals_create_together
---


Clubs, festivals and tours have closed worldwide due to pandemic.  In an industry dominated by steaming, where musicians rely on touring for almost all of their income, this has lead to a real crisis [for musicians](https://www.nme.com/news/music/a-third-of-musicians-could-leave-industry-due-to-coronavirus-new-study-says-2758172) and [live music venues](https://wjla.com/news/local/after-u-street-hall-closes-struggling-dc-venues-concerned-for-future).  In an effort to adapt, many musicians have turned to virtual concerts. 

![](https://edmidentity.com/wp-content/uploads/2020/05/SecretSky1-696x399.png)

But without a shared connection between audience and performer we miss something. I took the opportunity of my final JS project to build an experiment in restoring that shared experience: a collaborative framework for fans to create the visuals for virtual concerts TOGETHER.

![](https://i.imgur.com/xi4Krok.jpg)

In Collab Visuals, fans share visual “seeds” which drive animation on the main screen, built on a generative framework of cellular automata. Intuitive controls allow for real time visual tweaks and effects. A Rails backend supports thousands of fans seamlessly. A 100% Javascript frontend built on ThreeJS and WebGL means no app to download - and smooth performance on laptops, tablets, and phones. Even when we are apart, we can create something together.

![](https://i.imgur.com/dTgkj8u.mp4)

The project was challenging but rewarding to work through. There were three main areas in particular that went beyond what I'd covered in my Flatiron curriculum and really forced me to consider multiple approaches until I found the best solution. 

The biggest challenge was, without a doubt, working through the cellular automata algorithm. While the classic cellular automata - John Horton Conway's [Game Of Life](https://en.wikipedia.org/wiki/Conway's_Game_of_Life) - dates back to 1970, I wanted to push myself to create something new from the ground up. I also wanted to bring my perspective as a designer and animator to the project, and try and create something that was really unique. Finally, I wanted to add an element of managed randomness to each of the rules, to avoid the static and repeating nature of many cellular automata. At the most basic level, cellular automata revolve around each cell in the matrix determining the next step in their "life" by looking at their neighbors. How many are there? How old are they? How old am I? The tricky part is coding that behavior in an elegant way. When dealing with a large matrix of cells, every loop through the matrix has to be efficient or performance can quickly deteriorate.

Performance was the second challenge. A big goal for my project was to run on the widest possible range of hardware. A musician streaming a virtual concert from his bedroom is likely going to have a laptop - at best. The WebGL acceleration enabled by the ThreeJS framework was critical in getting good performance and framerates, but it wasn't a magic bullet. My initial class architectures featured a "maximal" cell object that encapsulated many other material and geometry objects, describing every possible aspect of the cell. I quickly learned that this approach absolutely killed performance - loops through a massive matrix of bloated cell objects lead to the twin death knells of straining laptop fans and horrible framerates. I had to pare down my central cell class until I had a system that ran smoothly even on my old iPhone 7. Performance took a lot of work - and it's the part of the project that I am probably the most proud of. 

The final challenge: front end styling. I wanted the system to be mobile first. For past projects, I'd used the Bulma framework. But this time, I had to create a more complex UI that allowed users to create their visual seeds. This meant a custom frontend build on a base of Bootstrap - which lead to rounds of frontend testing and revision to get the system working on both Chrome and the all important WebKit. Creating a good solution required deep dives into CSS Grids and other front end frameworks not covered in the curriculum. 

This my most challenging project yet. I'm happy with how it came together - and looking forward to continuing through to my final Flatiron project. To see Collab Visual's cellular automata in action, [check out this video.](https://invisiblelightnetwork.com/2020/10/22/collab-visuals/)
