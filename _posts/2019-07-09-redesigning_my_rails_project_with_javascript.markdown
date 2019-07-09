---
layout: post
title:      "Redesigning my Rails Project with Javascript"
date:       2019-07-09 19:54:27 +0000
permalink:  redesigning_my_rails_project_with_javascript
---


For my Rails-JS project, I chose to give some attention to an area of my WeekendGetaways project that I didn't spend much time on initially, as I thought it would be a good opportunity to improve the functionality of my project while showcasing my javascript skills. I re-worked the index, show and create actions of my Travel Agencies object, which is related to my main Getaway object through a has_many relationship (getaways belong to travel agencies).  Before this project, I was merely displaying agencies and the title of their getaways. Now, agencies are displayed with a link to each agency's show page, which contains a link to each getaway belonging to that agency. 

One of my favorite parts of this project was working with JSON serializers. I love how serializers give you so much control and flexibility over the data they return, making it easy to deliver exactly what you want when responding to API requests. 


