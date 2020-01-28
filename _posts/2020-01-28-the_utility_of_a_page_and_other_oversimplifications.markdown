---
layout: post
title:      "The Utility of a Page and other Oversimplifications"
date:       2020-01-28 11:39:52 -0500
permalink:  the_utility_of_a_page_and_other_oversimplifications
---

A few weeks ago I decided that I wanted the challenge myself to start reading the literary canon. I spent a few hours going through a great books lists and inputting information from them into a spreadsheet. I considered many ways of decidinging on the ordering of the books. I played around with ordering by date, influence, GoodReads reads, and Google Scholar citations. In the end I decided to create an algorithm that would calculate a yield for me based on the length of the book and the time it would take me to read each page.
It seemed that rather than looking to get maximum influence per book, if I instead looked to increase the total influence per page, my total “read utility per minute” would be the highest. Thus, my calculation was (log(GoodReads reads)*log(Google Scholar Citations)*GoodReads rating)/(Pages * Estimated Minutes per page). Here are a few example yields:

Experience and Education, John Dewey - 61 (~ 50 pages)
To the Lighthouse, Virginia Woolf - 33 (~ 250 pages)
An Inquiry into the Nature and Causes of the Wealth of Nations, Adam Smith - 7 (~ 1250 pages)

In the end, I was happy with the output of this but disappointed that it took 3 hours to input 80 books.
 
A week or so later I stumbled onto a website that had done much work for me. Thegreatestbooks.org already ranked the book via an algorithm and I thought that the ordering made a lot of sense. What I wanted was to be able to get more information about each of the books, like price and rating. My initial thought was to create a program that would search goodreads for each of the books and would return this information. I found, though, that the list already had the amazon links embedded in it so I decided to use amazon instead.

My great books collector CLI program accomplishes all these things. It scrapes the book data from multiple pages of the thegreatestbooks.org website and can get the amazon information on any of them by scraping it from the amazon page. 
There are a few additional features I would like to add. Right now, the scraping from amazon is pretty intensive and that’s why the program only scrapes amazon on request. I’d like to find a better way to get data from amazon and also add in information from GoodReads. With this I’d like to have it so that the books could be sorted based on different metrics. The highest priority addition is page count which I did not include in this version because it is placed obscurely on the amazon page in an ordered list and is in a different spot in the list depending on the book.

Overall I enjoyed making this project and learning more about scraping through it. I plan on this being a prototype for a more elaborate book listing program to come.

