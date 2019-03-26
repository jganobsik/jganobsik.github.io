---
layout: post
title:      "StockIndex, a Ruby CLI App"
date:       2019-03-26 02:56:54 +0000
permalink:  stockindex_a_ruby_cli_app
---


For my CLI Project, I chose to build an app that scraped the NASDAQ website to retrieve information on major stock indices. As a business student, I was exposed to a lot of financial theory during my  undergraduate studies, and I wanted my first project to reflect that part of my life. Building a stock index scraper was a fun challenge, as it forced me to deal with numbers and rapidly changing data. 

One of the more interesting challenges I faced when building this application was figuring out how to accurately determine whether the index was positive or negative for the day. NASDAQ's website uses arrows and css coloring to portray gain/loss on their page, and targeting the span elements containing the arrows with nokogiri proved difficult. Instead, I opted to compare current price to the previous day's close, which allowed me to accurately determine gain or loss based on whether the current price was larger or smaller than the prior day's close. 

My StockIndex CLI App can be found at: https://github.com/jganobsik/stockindex

I enjoyed blending familiar concepts with my new programming knowlede. I hope to expand StockIndex to handle stocks as well as indices, and add more data fields such as 52 week range.  
