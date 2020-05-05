---
layout: post
title:      "Connecting New Yorkers to food banks"
date:       2020-05-05 02:48:57 +0000
permalink:  connecting_new_yorkers_to_food_banks
---


The economic crisis created by the COVID epidemic has lead to severe financial hardship for many New Yorkers.  Massive lines at food banks have become a sad sign of the times both in [New York](https://twitter.com/bradlander/status/1254872997132984320) and [across the country](https://www.motherjones.com/food/2020/04/these-photos-show-the-staggering-food-bank-lines-across-america/).

An real challenge for families needing food bank assistance is how difficult it is to find even the most basic information - part of a larger pattern of [barriers that exist for the disadvantaged in the US](https://www.theatlantic.com/business/archive/2014/01/it-is-expensive-to-be-poor/282979/). 

Most of us are used to services like FreshDirect, GrubHub, Seamless, and DoorDash delivering groceries, meal kits, and takeout 24 hours a day.  In stark contrast, searches for food banks in Google Maps return limited and incomplete information [even in major cities like New York](https://www.google.com/maps/search/food+banks/@40.7055749,-73.9973371,11.84z).

More comprehensive food bank directories do exist - but are [difficult to use](https://www.google.com/maps/d/u/0/viewer?mid=1uVjjVxXfLFU4R6V7qjXXRoxCy-IwfMSP&ll=40.660927929148%2C-73.8646471568735&z=12). And food banks are often open for limited hours that vary widely from provider to provider. 

Which food banks are open near me when I am free? What is the best number to call for more information?  Getting answers to even basic questions can require clicking on dozens - or even hundreds - of seperate links. This is a real problem that tens of thousands of New Yorkers face every single day.  It shouldn’t be this hard for a struggling family to find food in New York City.

The good news? We can help.

My CLI project uses data from Food Bank for NYC and makes it simple to find nearby food banks at a time that is convenient for you in under a minute.

This was my first coding project, and as such was both rewarding and challenging in equal measure. 

I hit the first speed bump right out of the starting gate. Food Bank for NYC had all of the information I needed - but because it used JavaScript to deliver the data, it was nearly impossible to scrape.  Luckily, a little research presented a solution - the data could be exported as a KML file, an XML variant that was easy to handle with Nokogiri.

My second challenge: how to determine if a food bank is open when the user is available? We hadn’t worked with dates and times yet, but the fantastic support for Ruby online made it easy to get up to speed with the Time and Range classes, as well as the very cool === operator, making quick work of the problem.

Finally, the need to calculate distances between the user’s address and food banks necessitated location and API work - specifically the GeoKit Gem and Google’s Geocoding API.  This lead to several additional challenges, the first of which was how to prevent the private API key from ending up on GitHub, which .gitignore and the great dotenv Gem solved. The second challenge was how to best to optimize API access. Depending on the time of day, the program needed to make dozens - or even hundreds - of Geocoding API calls to find the closest food banks. This ended up slowing each user search to an annoying degree. My solution was to front load the process to get location data for each food bank during the initial scraping run. Once this initial startup was complete, every search executed almost instantaneously.

Fantastic help from Dustin Anderson’s office hours, Beth Schofield’s Eden Project walkthrough, and classmates on Slack were hugely important. I’m happy to have finished. My number one goal for this project was to create a real solution to a real problem. I hope to revisit this codebase as I continue to study, with an ultimate goal of getting it online and in the hands of people who need it.

For more, check out the repo at: https://github.com/elliotblanchard/food-bank-cli
