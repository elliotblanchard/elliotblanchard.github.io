---
layout: post
title:      "Want to put your CLI project online? Here’s what I learned."
date:       2020-08-16 19:46:51 +0000
permalink:  want_to_put_your_cli_project_online_here_s_what_i_learned
---


For my first Flatiron project, I built a CLI tool to help New York City residents find a food bank. NYC is experiencing record food insecurity during the pandemic, and finding an open food bank near you is time-consuming, frustrating, and inconvenient.  Finding food aid in NYC shouldn’t be as hard as it is now. I built a tool that solved all of these problems, and I wanted to get it out there. Once I finished my Sinatra project, I decided to double back to get my CLI project online. How hard could it be?

<iframe src="https://giphy.com/embed/Ur1EI6UyWsxA0caTd9" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

Unsurprisingly, the process was more complex than I had anticipated. In fact, It took longer to launch my CLI project [as a live Sinatra app](https://foodbanks.nyc) than it did to write the original code. The process took me outside of the Flatiron curriculum, forcing me to act independently. But it all worked out, and I’m glad I did it. Here is what I learned if you are thinking of doing something similar for one of your Flatiron projects. 

**CLI, meet MVC**

The first cut is the deepest. Sure, my CLI app worked great - but Sinatra follows a Model/View/Controller architecture. Transitioning the code to MVC in a smart and consistent way takes real thought and effort. Don’t rush this step. Taking shortcuts here can lead the confusion and poorly organized code that makes it more difficult to QA and finish. 

**Make it pretty**

<iframe src="https://giphy.com/embed/jQnU8XA7Nuv9SdZW7f" width="480" height="245" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

If you want to put your project online - and expect real people to use it - you have to implement a real front end. No one cares that a site was built by a student - if it isn’t usable, no one will use it.  And people have high expectations. The good news? There are a lot of resources available. 

**Bulma**

After a bit of research and some good advice from the Flatiron community, I settled on Bulma (https://bulma.io/)  as my front end framework. Bulma is exceptionally easy to use, and the support online is fantastic. Bulma is also designed to be mobile FIRST, which is critical for any modern site (more on this later) 

**Meet Google, your new best friend**

[My food bank app](https://foodbanks.nyc) is location-based, so I use Google’s Maps and Places services to enhance the user experience with location intelligence and interactive maps. Integrating the JavaScript for this functionality was a bit of a lift - but worth it.  Users don’t have to input long addresses, and could see their search results on a custom Google Map: making it easy to get directions to and contact food banks. 

**Meet Heroku, your OTHER new best friend**

<iframe src="https://giphy.com/embed/l4KhXO06gtMQbomIg" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

Sharing your project with the world means finding a good hosting provider. For most of us, that means Heroku. Heroku is a great choice, but getting your Sinatra app live on Heroku the first time can be challenging. There’s a lot to consider, and a lot to set up. The biggest hurdle: the database - Heroku does not support SQLite, so you need to switch to PostgreSQL on both the dev AND production side for your app to run smoothly. Setting up PostgreSQL on OS X is fairly easy, but getting everything updated and working on Heroku can be complex. Luckily, the Flatiron community helped enormously. Christine Tran wrote a fantastic guide for deploying a Sinatra app to Heroku:  

[https://medium.com/@christine_tran/deploying-sinatra-app-to-heroku-8c64f025db77](https://medium.com/@christine_tran/deploying-sinatra-app-to-heroku-8c64f025db77)

Heroku’s docs also have a great guide to getting started on Heroku with Ruby: 

[https://devcenter.heroku.com/articles/getting-started-with-ruby?singlepage=true](https://devcenter.heroku.com/articles/getting-started-with-ruby?singlepage=true)

As Christine mentioned in step one of her guide, getting comfortable with the Heroku command line tools is critical to deploying successfully and maintaining your deployment post-launch. I found this to be a good introduction to getting started with the CLI:

[https://devcenter.heroku.com/articles/heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)

Getting familiar with Heroku was a real commitment the first time, but it clears the way for future projects. 

**QA: This time, we mean it**

<iframe src="https://giphy.com/embed/3owzW2E0spG6KRlRIs" width="480" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

QA takes on a new meaning when you launch your app to the world. Different browsers, different devices, different users - everything has to work. Even the hosting provider (ever wonder what time zone your server is in?) can spawn new and exciting bugs. Look forward to your friends reporting bugs on systems you don’t have. Launching your app means respecting your user and delivering a smooth experience.

**Mobile first**

Remember Module 11 / Section 3 - Responsive Design? Hope so, because most of your visitors are going to be visiting your site on a device other than a PC. Your site has to look good - and be usable - on everything from a PC to a phone. 

I had some initial concerns, but the Bulma framework was a huge advantage. Bulma was built to be mobile first from the ground up, and made the process of responsive design a very smooth one. But there’s more to making a responsive website than the design. It has to be usable and convenient for mobile devices without a full keyboard. Once again, the Flatiron community was a huge help - Danny Lee forwarded me this fantastic guide on best practices for mobile form design:

[https://www.smashingmagazine.com/2018/08/best-practices-for-mobile-form-design/](https://www.smashingmagazine.com/2018/08/best-practices-for-mobile-form-design/)

**All you need are users**

<iframe src="https://giphy.com/embed/UryNyQro5QkSHqmEuE" width="480" height="279" frameBorder="0" class="giphy-embed" allowFullScreen></iframe>

You did it - you launched your site. Now what? Remember why you did this in the first place - to get your app to users. But that doesn’t happen by itself. Make sure to set aside time to share and promote your site once you’ve launched it. It is real work - and it takes time. Getting the word out there and following up is tough, but it’s rewarding as you see your audience grow. 

**Results!**

Once you launch, the hard work starts to pay off. [foodbanks.nyc](https://foodbanks.nyc) - the first app I wrote at Flatiron - is now live for anyone to use. From the appreciation I’ve gotten from regular users, to thank you letters from the city council members and state assembly members - it means a lot to see my hard work being appreciated and making a difference in people’s lives. 

