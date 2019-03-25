---
layout: post
title:      "CLI Project Struggles"
date:       2019-03-25 15:39:29 +0000
permalink:  cli_project_struggles
---


While building my CLI Project, I spent a lot of time attempting to extract certain elements from css tags on Yahoo Finance. Due to some unforeseen complications with the way their site is set up, I was getting multiple elements back every time I scraped the site, not just the elements I was looking for. I spent a lot of time looking at possible workarounds, and came back with 3 solutions: 

1) Push each element (in this case a single word or number) into an array and loop through that array to find the data I 
was looking for.

2) Assume that the elements at a certain index would always be correct, so use the element at that position

3) Find a more nogokiri-friendly site to get the same data


I ultimately went with the third option, as I found many other people chose to scrape the NASDAQ website for stock data. 


This experience taught me to take a step back, evaluate my options, and weigh the implications when hitting a roadblock with your code. I know I will encounter similar situations in the future, and can use this same process to find the best path forward.
