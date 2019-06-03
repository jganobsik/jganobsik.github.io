---
layout: post
title:      "WeekendGetaway, a Trip Organizer and Idea Board built on Rails"
date:       2019-06-03 16:44:19 +0000
permalink:  weekendgetaway_a_trip_organizer_and_idea_board_built_on_rails
---

Now that we are getting close to the holiday weekends of summer that many people use as an excuse for a weekend trip, I thought it would be fun to build a rails web app that allows you to outline your trip and get inspired by other users' trips as well! My rails project, WeekendGetaway, blends functionality and social features to create a space for trip planning, ideation, or just browsing others' trips to get ideas for the future.  It helps you plan for both the trip and destination, allowing you to specify what type of trip you are planning (flight or road trip), how long your trip is (must be between 2-4 since this is a weekend getaway), where you are staying, and whether you used an agency to plan your trip.


On a technical note, one of my main takeaways from this project is to ensure that your models are conveniently named, and to properly namespace your routes to avoid confusion. Programmers have a large degree of flexibility when naming models, which is definitely a double-edged sword. I found this out when naming my accommodation model, which caused me quite a bit of grief when creating my nested form for a getaway. A lot of my views involve calling the city which your hotel or lodging resides in, which serves as a convenient way to get the destination for a getaway. However, I discovered that the city wasn't able to be called, and I had no idea why! After digging around in the create action, I discovered the root cause of this problem: My form was missing a 'm' when rendering the accommodation fields, causing the content to be rejected as not part of my permitted parameters. A simpler model name would've made it easier to see this error, and I will strive to employ better naming practices in the future. I also learned that namespacing routes is very beneficial when linking to various parts of your application, as it allows rails to deal with the handling of specific links and makes your code much cleaner and more readable.

Overall, I found Rails to be very pleasant to work with, and enjoyed learning about the various features and helpers that make it simper to perform common tasks. I look forward to integrating Javascript into my project and further refining my web app!

My project can be found at: https://github.com/jganobsik/WeekendGetaway

