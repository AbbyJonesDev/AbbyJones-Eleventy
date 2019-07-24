---
title:  "My First Angular App"
date:   2016-02-02
summary: ""
tags: 
   - JavaScript
   - AngularJS
   - freecodecamp
---
One of the Intermediate Front End Development projects for FreeCodeCamp is to build a [Local Weather App](http://www.freecodecamp.com/challenges/show-the-local-weather), a single page app that uses geolocation and a weather API to show the current weather in a user's location.  They recommend using the [Open Weather API](http://openweathermap.org/api).  Requirements include providing a button that toggles units between Celsius and Fahrenheit and setting a different icon or background image based on weather conditions. 

I decided to take things a step further by adding a zip code search and a 5-day forecast along with current conditions.  This project was also a great opportunity to take Angular out for a test spin. 

Check out the project on [CodePen](http://codepen.io/AbbyJonesDev/full/zrEazz/).  There are still some things I would love to make better, but it's been a great learning experience.  Before I move on to the next project, here are some takeways from this one:


*  Good API documentation is invaluable.

*  Using a console.log statement to grab data coming back from an API call is a handy way to inspect it more closely.  Very helpful for debugging and also just seeing exactly what you're getting back from the service.

*  Sometimes API's do surprising things, like providing dates in different formats in different calls or parts of a call.  

*  Chrome is good at interpreting dates given in different formats.  Safari and Firefox are less forgiving.  To be safe, you can parse the date string from the API and pass it along to the Date constructor in standard ISO format, or just leave it as is.  (But if you want to use [Angular's date filters](https://docs.angularjs.org/api/ng/filter/date), you need to provide a Date object or something the browser can translate into a Date object.)

*  You have to multiply a Unix timestamp by 1000 to get JavaScript time, because Unix gives dates in seconds, but the default JavaScript Date constructor expects milliseconds.  (Both are based on January 1st of 1970.)

*  It's AWESOME to watch how lightning fast Angular can update the view in response to user interaction and even new API calls.

*  Angular usually picks up changes in the scope right away, but sometimes you have to call ```$scope.$apply()``` to trigger the digest loop and let Angular know about the change.

*  You can create your own [Angular filters](https://scotch.io/tutorials/building-custom-angularjs-filters).  This is pretty handy and not that tough.

* Angular directives are very cool and very powerful.  They also add up and make the markup start to feel cluttered.  Hmmm...  There might be better approaches for handling this that I'm not aware of yet.

*  Different browsers handle geolocation in slightly different ways.  This can be aggravating.  The main place I ran into this issue was in trying to provide a graceful fallback for users who chose not to share their location data.  My current implementation works well on Chrome and Safari but not on Firefox.

*  Geolocation can take a long time.  This can be aggravating.  It can also make it look like your page is dead in the water.  Definitely provide a message and update it as needed so users know what's happening.  Setting a sensible timeout is probably a good idea as well, and then providing users with an easy alternative method for entering a location so they can accomplish their goal as quickly and easily as possible.


**And some things I'm still working on...**

*  How to use plain old JavaScript objects in concert with Angular to keep things clean and organized

*  How to organize code into separate files and wire it up together (You just get the one js file in the free version of CodePen, so everything goes there.)

*  When to use "this" vs "var" when defining properties and methods inside of a function, and how to make functions defined in a function available to other functions in the same function.  (This is still harder to wrap my head around than writing classes and class/instance methods in Ruby, but I'm getting there...)