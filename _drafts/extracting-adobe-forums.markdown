---
layout: post
title: Extracting Data from Adobe Forums
---

Quick "hacked-out" way to do data mining on the rich data found in the Adobe Forums.
I'm doing research where I have to gather data from a few support forums in the web.

Here's an exploratory post detailing the steps I went through in this journey.
I actually went through a few hours of roundabout hackery with Yahoo! Pipes.
That went alright, until I found out that Yahoo Query Language (YQL) is the new way to do the same thing.
I couldn't help but redo everything in YQL. (I'm aware that you can mix the two, but YQL is supposed to *replace* Yahoo Pipes)
So here goes...

Did some Firebugging on the Adobe Forums to find that AJAX requests were made to the following url.

http://forums.adobe.com/view-threads.jspa?containerType=14&container=3340&start=90&tagSet=-1&numResults=30&filter=all#

Some digging around in the software that is used for the Adobe Forums
http://www.jivesoftware.com/docs/clearspace/latest/WorkingWithClearspaceFeeds.html

Interestingly, there is even an FAQ for pulling data off ClearSpace Feeds.
[](http://www.jivesoftware.com/docs/jive_clearspace/latest/FeedsFrequentlyAskedQuestions.html)
So the following blah.
http://forums.adobe.com/community/feeds/allcontent?community=3340&numItems=40

There's not offset so I guess it's not as useful as the above view-threads url used in the AJAX.
That's it for the official help channels. I shall hack on.

--

@var is handy for the queries. I'm not sure what I'll use it for, yet.

A comment from [an experienced user's blog](http://arapehlivanian.com/screen-scraping-and-creating-a-feed-with-yql-and-yahoo-pipes/) has led me to turn to look at using Open Data Tables for my purpose.

