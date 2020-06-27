---
layout: post
title:      "The Broadband Co-Op: Sharing wifi with Sinatra. "
date:       2020-06-27 21:34:30 +0000
permalink:  the_broadband_co-op_sharing_wifi_with_sinatra
---


The ongoing COVID epidemic highlights how the digital divide shapes educational achievement in New York City. The crisis has forced millions of New York City students into remote learning.  With a vaccine still months away, remote learning is set continue throughout the 2020-2021 school year. This shift puts a new focus on NYC’s digital divide. Nearly one-third of city households [lack access to broadband at home](https://comptroller.nyc.gov/wp-content/uploads/documents/Census_and_The_City_Overcoming_NYC_Digital_Divide_Census.pdf). In some neighborhoods, as much as 50% of households lack access. Forty four percent of New Yorkers in poverty lack broadband internet access, as opposed to only 22 percent above the poverty line. 

Students in homes without broadband face huge challenges to success in remote learning - from participating in video calls, to doing homework and turning in assignments. The closure of city libraries compounds these problems by removing alternate locations where students can log in. 

The urban density of New York provides a potential solution. The [Open Wireless movement](https://www.openwireless.org/) promotes wifi sharing to democratize broadband access. In many ways, New York City is the perfect city for Open Wireless. High density neighborhoods means that a single apartment household can see WiFi from many neighbors. In an effort to help create a solution for the digital divide in remote learning, I built *The Broadband Co-Op*: a space for broadband owners to share their networks with nearby students. 

The Broadband Co-Op has two types of users: *students* can join to see shared networks that are available nearby. Students can also rate shared networks to help other students quickly choose the best option, and let network owners know of connection problems students may be experiencing. *Providers* can join to share their networks with nearby students.  Each provider can have many shared networks. 

Privacy was a key concern in the design of The Broadband Co-Op. Student information is protected. Providers never see student information or location - they simply receive a notification if *any* students are nearby. Provider network privacy is also respected. All provider networks are password protected. Only nearby students see network login information, and providers can easily change network login credentials and take a network offline. 

I found the build process for The Broadband Co-Op to be pretty enjoyable. Key credit for this goes to Ayana Zaire Cotton's fantastic four part Sinatra project walkthrough, and her very helpful office hours. While the core of The Broadband Co-Op built on what I'd learned in the Sinatra module, the location mapping in the project gave me a chance to revisit the GeoKit gem I had previously worked with in my [food bank locator](https://elliotblanchard.github.io/connecting_new_yorkers_to_food_banks) CLI project. The project also gave me a great introduction to Active Record's validation functionality, which I was able to leverage to painlessly check user input and validate emails. 

Building The Broadband Co-Op crystallized everything that I had learned over the previous weeks - I'm proud of the project and hope to explore options for getting it online in the near future to help New York students in need. 

Interested? Check out my Git repo for The Broadband Co-Op at [https://github.com/elliotblanchard/sinatra-final-broadband-share ](https://github.com/elliotblanchard/sinatra-final-broadband-share)
