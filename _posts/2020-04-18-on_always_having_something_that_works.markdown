---
layout: post
title:      "On Always Having Something That Works"
date:       2020-04-19 03:45:11 +0000
permalink:  on_always_having_something_that_works
---


Building the rails project previous to this one took me over two weeks, though for many of those days I was not actually working on it. Disheartened, I had moved on to studying the Javascript section while my project sat unsubmitted. When I finally returned to what I thought was a broken mess, it only ended up taking 2-3 hours to fix and get ready to submit. The problem was that it wasn’t really working until them.

I did everything for that project in massive horizontal chunks. First I wrote all the tests, for all features and models, before even opening my app directory. My plan was to build out everything I wanted to have and then follow the tests through development. The problem with this approach is rather than seeing if the new feature I had added had broken an old one as is the intention of tests, I was only getting fifty red x’s on my screen. It was not until the last hour before I submitted it that everything was finally passing.

I had built the rest of the application in the same way. I wrote all of the migrations, then all of the models, then all of the controller actions. This meant that when I got to writing views and realized that I had made a syntax mistake, I had to change it everywhere. It also meant that there was never a minimum viable product. 

Fast forward to the Javascript project where I did things entirely differently. Inspired by the recommendations in the project guidelines, I decided to build out each minute feature from start to finish before moving onto the next one. This meant that every half hour or so I was back to a completely functional, if limited, site. At first I thought that the main benefit to this was going to be speed, and as two days versus two weeks for a site with a similar amount of logic shows, it was. However, I think the biggest difference was that building this site was packed with tons of little treats where I got something working, if small, after working on it for a short time while the other was disappointment after disappointment.

I have learned thus far that it isn’t going to work right the first time that you run it, so the question is not whether you have to debug or not but for how long. My debugging spirit dries up in a few hours. Thus, with the previous project I took long, sometimes multi day, breaks when I was stuck. I think the greatest power of always having something that worked was that, even though I didn’t, I knew I could always reset to a little while ago when it was working and not lose that much. This allowed me to work on this project from morning to night and not lose steam where I ended up getting frustrated after an hour or so trying to debug the tangled mess of the other. I think it also led to much cleaner and less interwoven code in the end.

