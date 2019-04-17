---
layout: post
title:      "JerseyTracker, A Sinatra Web App"
date:       2019-04-17 23:15:42 +0000
permalink:  jerseytracker_a_sinatra_web_app
---


For my sinatra project, I chose to write an application that allows users to track their sports jerseys. I am an avid hockey fan, and I came up with the idea for this site after spending far too much time on reddit's r/hockeyjerseys one day.

The project allows users to create and edit their collection of jerseys from any sport. Currently, users can enter a title, player name, player number, and sport for their jersey. The project contains input validation and ownership validation when creating and editing jerseys, and secures user data using the bcrypt gem.

The biggest challenge I faced when building this project was a simple oversight on the jersey controller that prevented the jersey from belonging to a user. I spent hours double-checking my database setup and model associations, trying to determine why the user id of jerseys came up nil. I modified my forms countless times, and attempted several methods to grab the current user from the session. I fired up the Tux gem to see if I could create the association via the console. Finally, I found the culprit of this elusive bug: I was using Jersey.create instead of user.jerseys.create. I was so relieved when my code was finally fixed

One of my favorite parts of this project was experimenting with the Bulma CSS library (https://bulma.io/). It is a pure CSS framework that is easy to learn and implement, and gives your pages a unique, refreshing look that stands out from the generic bootstrap pages that are so prevalent nowadays. One of my favorite youtube channels, Traversy Media, created an excellent walkthrough that helps you familiarize yourself with Bulma (https://youtu.be/IiPQYQT2-wg).

I really enjoyed this project because it really demonstrates the power of using ruby on a website. While Sinatra can be tedious, and doesn't have the large community following of Rails, it allows you to clearly see how ruby works on a web app. 
