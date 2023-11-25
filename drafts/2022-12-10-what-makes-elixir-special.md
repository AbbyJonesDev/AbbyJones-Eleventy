---
title:  "What Makes Elixir So Special"
date:   2022-12-10
summary: ""
tags: 
  - Elixir
  - "Functional Programming"
eleventyExcludeFromCollections: true
permalink: false
---

This year has been another year full of learning 

AWS CDK - and migrating to v2

Writing Python again for the first time in years

Snowflake

Organizing an internal conference

And Elixir.  And the one that gets me out of bed in the morning is Elixir


## Standing on the Shoulders of Giants

Erlang - concurrency, scalability, fault tolerance.  "Cloud in a box"

Ruby - developer happiness, productivity.  Fueled so many startups, including big names like GitHub, Pinterest, Shopify, Twitter

React - declarative UI, functional, reactive programming for the front end, reusable components


## Brings Together the Best of Many Worlds

Like Java - it's compiled, which means the compiler catches a lot of errors for you.  And the compiler tends to give really helpful, detailed feedback.

Like JavaScript - it has hot module reloading in development.  Initial compile takes a bit of time, but after that, it does a smart recompile of only the things that changed.  Feels like the JS dev experience

Like Erlang - data is immutable by default.  I can't shoot myself in the foot by modifying something as I pass it around by reference.


## Above and Beyond

Testing library built in, ready to go with zero configuration.  Adding Phoenix brings in more helpers.  Adding LiveView brings in more helpers.  I don't have to go add more libraries and more configuration manually.  I just focus on my code my tests.

Documentation is an integral part of the language.  You can even write examples in the documentation that will be run as part of the tests and fail if it doesn't produce the expected output.  Adding one library and running one additional command will generate full HTML output of the documentation with the standard formatting and styling used across the community.

Livebook

Observability

Community

## So Why Isn't Everyone Using Elixir?

Risk in doing something different than the crowd

Functional programming feels scary.  Colleges teach OO.  Rumors that functional programming is hard and you have to be a math genius to use it.

Ecosystem is smaller than Java/JavaScript/Ruby/Python.  Not as many libraries out there.  Not as many experienced developers to create and maintain them.

Human resources - not as many out there

Security-related tooling is close but not quite there to the same extent as it is for other languages.  

## Work in Progress

Functional programming - all the amazing Elixir resources, similar syntax to Ruby, success stories

Ecosystem - growth related to AWS libraries, AI/ML, LiveView Native, keynotes from Chris Grainger and the Dockyard guy.  

Human resources - the training materials, and consultancies.  Dockyard, TestDouble, LaunchScout, Erlang Foundation(?).  Dockyard Academy.  LaunchScout apprenticeship program

Security-related tooling - recent support for SCA from GitHub, Snyk.  Dependency Track.  SAST available from GitLab, coming to Snyk.

## If you aren't using Elixir yet - don't count it out.