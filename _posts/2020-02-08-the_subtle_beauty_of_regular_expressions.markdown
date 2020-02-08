---
layout: post
title:      "The Subtle Beauty of Regular Expressions"
date:       2020-02-08 16:27:09 +0000
permalink:  the_subtle_beauty_of_regular_expressions
---

I have found that most guides to RegEx are devoted to laying out everything about it or enumerating all of its possible uses. Rather than this, I would like to show here a few test cases that the use of regular expressions lends itself to elegant solutions.

The first is capture groups, something that I have found very powerful when using it, but I found overlooked in a few guides.

Let’s say we have a chef friend who used to live in a city that we will be visiting in a few weeks. Over their years living there they compiled a list of their favorite restaurants and dishes at them there on the notes app of their phone. Sadly for us, their perspective on intermediary punctuation changed dramatically during the time that they lived there. Some of the items are separated by commas while others are seperated with a dash. For example,

One entry reads: Jimmy’s BBQ - Pulled Pork
While another says: Crusader Coffee, Scones

Our goal is to turn this information into a hash where the key is the restaurant and the value is the favorite dish. For this, capture groups will work great.

Our regular expression, after splitting the list based on lines breaks will read:
```
/(?<restaurant>.+)(\s-\s | \,\s)(?<dish>.+)/
```

Imagine if instead of .+ we had \w+ which would seem to make sense as we are looking for word characters. In this instance we would only collect “Jimmy”. Even if we added an optional white space character with \s?, what would happen when we reached Happy Wholesome Cakes, we’d be stuck again. Thus, it makes sense to base our collection on what we know will divide what we want to collect rather than the format of what we are collecting. The \, in this breaks the character. Breaking characters is especially useful when looking to collect a period character. If you simply put it,  “.”, into the regular expression this will collect anything that is not a \n character. To collect the period we could instead use \. which will escape the character.

Finally, putting it all together, to get the information and put it into a hash we could say, in ruby

```
list _array = list.split(‘\n’)
restaurant_hash = {} 
List_array.each do |restaurant_entry|
data = /(?<restaurant>.+)(\s-\s | \,\s)(?<dish>.+)/.match(restaurant_entry)
restaurant_hash[data[:restaurant]] = data[:dish]
end
```
For our other example, after we do this, our friend gets back to us with a new list they found buried even deeper in their notes app that also has the cost of each dish. Being the cheapskate we are, we want to take this data into account. Opening the list, we find something odd. While some entries are formatted as we would expect, others seem to have mixed characters. For example, City Lights Burgers, Bacon Extreme - $12.50. Our friend tells us that these entries, the ones with mixed “ - “ and “, “ came at a difficult and listless time in their life and should thus be disregarded. We know we could create a different expression for each case, but we got into the regular expression business to find elegant solutions, not to repeat ourselves. We find our solution in branch reset groups. Our expression is

`/(?<restaurant>.+)(\s-\s | \,\s)(?<dish>.+)\2(?<=\$)(?<price>.+)/`

The \2 asserts that it needs to be the same as the reference it points back to. Thus, if the first divisor is a “ - “, the second one will need to be as well. The other new thing that this solution adds is the (?<=\$). This is a non capture group meaning that it’s data[:price] will not contain the “$” character, but we assert that it needs to be there for our price capture.

