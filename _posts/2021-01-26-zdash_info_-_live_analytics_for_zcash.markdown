---
layout: post
title:      "Zdash.info - Live analytics for Zcash"
date:       2021-01-26 16:43:30 +0000
permalink:  zdash_info_-_live_analytics_for_zcash
---


For my final Flatiron project, I wanted to push myself and build something that could serve as a real transition to the professional world: a project that solved a real problem for real stakeholders.

I created [Zdash.info](https://www.zdash.info): a live analytics dashboard for the Zcash cryptocurrency. Zcash is one of the only cryptocurrencies that offers true privacy for accounts and transactions - unlike Bitcoin, Ethereum, and most other blockchains. I had the good fortune to meet Ian Miers, one of the creators of Zcash, at a tech talk. 

![](https://media.giphy.com/media/Xtg9ygGsjvouF7vZ1w/giphy.gif)

I followed up with Ian to see if there were any pressing needs for the community. While Zcash is a blockchain built around privacy, there was no source of live analytics tracking these private transactions. The only data available were static reports produced - at best - every few weeks. The size of the data set - about 2.2 million transactions a year - and the complex analysis needed meant that Zcash was missing a critically important data source online. This was a perfect opportunity to make a real impact.

[Zdash.info](https://www.zdash.info) is built on a Rails backend and a React/Redux/Thunk frontend. Communication between the backend and frontend is via RESTful API calls. The key challenge for the backend is to efficiently fetch and manage the large volume of blockchain data needed to produce the analytics. For historical transactions, the backend uses RPC calls to a Zcash CLI blockchain utility using the [rpc-json](https://rubygems.org/gems/rpc-json) GEM: over a year of data comprising over 2.2 million transactions can be analyzed in only a few hours on a “vintage” MacBook Pro. For ongoing transactions, a scheduled Rake task connecting to a public API of Zcash transactions supplies the backend with the latest data. Use of the [activerecord-import](https://rubygems.org/gems/activerecord-import) GEM allows for high volumes (thousands at a time) of transactions to be added to the PostgreSQL database.

![](https://media.giphy.com/media/xTiTnKwDwRpWumX2py/giphy.gif)

The frontend is a single page application built on a React/Redux/Thunk framework, using a hierarchy of react-router routes, containers, and stateless components. Redux is used to manage and modify state change, while Thunk acts as middleware for async requests to the backend via RESTful API calls. The overall styling for the frontend is handed via the React-Bootstrap framework. Our charts, the heart of [Zdash.info](https://www.zdash.info), use the [Nivo library](https://nivo.rocks) of dataviz components. Nivo allows for SVG based, interactive, animated charts that look fantastic and are endlessly flexible. 

Key challenges fell into two overall categories: working with stakeholders to identify and understand key goals, and optimally managing the large dataset. Identifying and classifying private transactions on the Zcash blockchain - and to what degree they are private - required a fairly deep understanding of the technical foundations of the cryptocurrency. I was fortunate to have a fantastic group of stakeholders to advise me during the development of [Zdash.info](https://www.zdash.info), including several key figures in the Zcash community. Understanding these business goals enabled a successful project.

On the technical side, the key challenge was the amount and volume of blockchain transaction data that needed to be managed. At roughly 2.2 million transactions per year, the data requirements for [Zdash.info](https://www.zdash.info) were exponentially larger than my other Flatiron projects. The backend needed to keep up with a high volume of incoming transactions, while the frontend had to maintain fast response times, even when dealing with full-year charts that query millions of transactions. I quickly realized that adding individual transactions to the Postgres DB was suboptimal. As the database grew, import speed quickly fell below the rate at which new transactions came in. The solution was the fantastic activerecord-import GEM. Instead of adding transactions one at a time, activerecord-import allows for thousands of transactions to be imported at once, vastly increasing import speeds and making it easy for even my older laptop to process an entire year of transactions in only a few hours. On the frontend, even with indexing, response times were unacceptably slow - especially the dreaded (but popular) full year charts. The solution here was realizing that the data for these charts was complex - but rarely changed. Even the more current daily charts only added a new entry hourly. This allowed for a custom caching functionality that increased response time by a factor of 100, leading to fast response times even for huge datasets. 

![](https://media.giphy.com/media/l4RKhOL0xiBdbgglFi/giphy.gif)

The great response of the Zcash community to [Zdash.info](https://www.zdash.info) has opened up several avenues for future extensions to the site, including detailed data on shielded pools and custom date ranges in charting queries. Even better, there have been several requests to make [Zdash.info](https://www.zdash.info) an open source project so that community members can contribute functionality to the site. I look forward to continuing to improve and expand the site. 
