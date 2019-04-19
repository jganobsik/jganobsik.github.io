---
layout: post
title:      "Harnessing the Power of ERB"
date:       2019-04-19 23:47:38 +0000
permalink:  harnessing_the_power_of_erb
---


I spent most of today improving my Sinatra project, JerseyTracker. One of the biggest changes I made was to the index page. When I initially submitted my project, I used Bulma's Card elements to display each jersey by creating a new card when iterating through all existing jerseys on the index page. While this looked better than displaying basic, unformatted HTML, the cards looked awkward and stretched across larger screens. To fix this, I decided to display jerseys in 3 separate columns.

My original code for the index page looked something like this:

```
@jerseys.each do |jersey|

#create a new card and fill it with jersey details

end
```

Initially, I thought that i could use each_with_index and use the index to assign a column. However, I quickly realized this was neither a simple nor elegant approach to placing columns. 

After more investigation, I decided that using the each_slice method would be the perfect way to solve this problem. I was able separate jerseys into chunks of 3, and then iterate through each chunk to create 1 column and 1 card per jersey instance. Here is a section of the code I used to accomplish this:

```
<% @jerseys.each_slice(3) do |jersey_slice| %>

<div class="columns">

<% jersey_slice.each do |jersey|%>

<div class="column">

#create card

end
end
```


Getting this to work really demonstrated the benefits of using Ruby for web development, and the power and flexibility of ERB. Solving this problem helped me to fully understand the benefits of being able to use the wide range of methods Ruby provides in your views, and made me appreciate ERB even more.
