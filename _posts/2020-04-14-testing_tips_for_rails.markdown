---
layout: post
title:      "Testing Tips for Rails"
date:       2020-04-14 12:17:56 -0400
permalink:  testing_tips_for_rails
---


I made a test suite for my rails project. This was my first time writing extensive tests in rails and I learned a lot through it, the most significant thing being that writing your tests can very likely take longer than writing the code for your application.

**# Use Factory Bot**

I started this project simply creating instances of my models to use in my tests, but as I researched my I discovered that Factory Bot is a faster, easier, and more flexible option. A helpful feature of Factory Bot is being able to make traits. This allowed me to set when an object was inactive in my factory as a trait and apply it to the instance created in my test. This way if I wanted to change what the definition of inactive was I only had to change it in the one place in my factory not with every inactive object I created in my tests

**Write feature and model tests rather than controller tests.**

I found when researching controller tests that they are going out of vogue. I think this is for good reason. They are very inflexible and are hard to implement from user stories. For my test suite I used extensive feature and model testing instead. I found that feature tests are a much more useful cousin of controller tests, their best attribute being that they are easy to implement from user stories.

**Use Devise Helpers in Feature Tests**

Using devise helpers (if you are using devise) instead of creating your own sign in and sign out helpers will save a lot of time. As long as you create a factory with all the required attributes for their sign in, they are remarkably easy.

**Use lots of context and describe statments**

I found it incredibly helpful to have my tests nested within describe and context blocks. Putting the whole sentence after ‘it’ will take away a lot of the readability of rspec tests. A good rule of thumb is to simply put the method the tests are describing, usually just one or two words, in the describe and then put any part of the sentence that starts with ‘when’, ‘with’, or ‘without’ in a context block. At the end the flow through all of your blocks should form a complete sentence.


