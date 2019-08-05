---
layout: post
title:      "TutorChat: a platform for tutors and educators"
date:       2019-08-05 17:51:31 +0000
permalink:  tutorchat_a_platform_for_tutors_and_educators
---


For my final project, I wanted to make something that could potentially be turned into a full-fledged platform that people would be able to use. Over the past 2 months, I have been buiding TutorChat, which is a platform targeted at tutors and educators that allows them to create appointments that can be booked by students and participate in live chat sessions.

Since I would like this app to be deployable, I wanted to create a production-grade rails api that utilizes commonly used tools and best practices, such as the Devise user gem, JWT for user authentication, ActionMailer, and JSON serializers. While it took longer to set up than a basic CRUD API, I am definitely glad I took the time to go through this process, as it was an excellent learning opportunity and made my application better.

I used react to create a beautiful, simple frontend. One of the more challenging aspects this booking platform was determining how to handle the setting of appointment times. Thankfully, I came across moment.js and a date picker component by YouCanBookMe, both of which had excellent documentation. I eventually decided to utilize 2 date pickers to allow users to set any start and end time, making the platform very flexible for the user. I am currently enforcing validations that require the start time to be earlier than the end time, as well as preventing duplicate or overlapping appointments from being created. 

I implemented a Talk.JS chat client as well, which allowed me to quickly get a chat system up and running instead of building one from scratch.

In the future, I would like to add additional validations to the appointments such as time constraints, as well as implement a default appointment length. I would also like to add alerts and notifications, as this would enhance the feel of things like creating appointments and recieving messages.
