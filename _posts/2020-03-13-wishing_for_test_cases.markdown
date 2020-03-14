---
layout: post
title:      "Wishing for Test Cases"
date:       2020-03-13 20:27:42 -0400
permalink:  wishing_for_test_cases
---


I have been trying to write more letters to people and built a Sinatra application that I can put letters into when I send them and then mark as received when I get confirmation that they have arrived. 

I thought beginning my Sinatra project that I wouldn't need to use test cases because it did not seem like there would be that much going on in my app and it would be easy to test. However, by the end, I realized that what I had earlier thought would be a waste of time was now leading me to have to check my site repeatedly and be concerned that I wasn’t checking everything. After this project I will use test driven development and I thought that I would give some reasons why it makes the most sense even with the initial time investment. 

**It provides structure while you code**

The point of test cases is not exclusively to check that things are working. It also helps give you an organized workflow for building your application. By starting with the first test case and getting them working one at a time you can avoid making the error I made multiple times in this project. Rather than doing one small task at a time, I would set up a whole page. The problem with this was that I would have many mistakes in the code and they might be reliant on each other. Rather than knowing exactly where the problem was because I had only changed one thing, I was left having to hunt it down.

**It checks to make sure everything is working**

This may seem definitional, but I think it is important how powerful this is if you truly follow test driven development. This might not be true if you don’t do exactly what the test case is asking for and instead extend functionality without having the proper tests first. However, in theory if your code is only responding to the next test there will not be anything your tests aren’t checking. Not using test driven development, I forgot to check one of the scenarios on my newsletter page and ended up having to stop my demo recording and fix it.

**It lets you pick up where you left off**

I started this project believing that I would be doing it in one or two days so wasn’t too worried about knowing where I left off, but life got in the way and I ended up doing it for an hour or two a day for a week. This left me coming back to my project and not knowing what needed doing next. Thus, I wasted extra time.

**It keeps you from going past what is necessary**

Because I didn’t have any tests that I was working to complete, I ended up spending a good bit of time on some rather trivial components of the app. If I had created test cases I would have already created as scaffolding for what the most necessary components of my application were and would have been able to follow it.

**It can check that everything is working again, and again, and again**

I thought that I had made the right choice until I was checking my apps functionality for the second time. I was certain I had made the wrong one when I was checking it for the third time. With a test suite you can be certain with every change you make the rest of your application is still working. Small changes can have domino effects into other older code.

