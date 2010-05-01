---
layout: default
title: Messing around with Yahoo! Pipes
---

Playing around with the Yahoo! Pipes and spent an hour working on the Regex module until I found that the source of the problem was a bug with their S flag. 
It's documented at [the forum](http://discuss.pipes.yahoo.com/Message_Boards_for_Pipes/threadview?m=te&bn=pip-DeveloperHelp&tid=4415&mid=4415&tof=131&frt=2#4415).
Basically, assume that the "s" checkbox doesn't work. Always use the `(?s)` flag explicitly in the regex pattern to prevent any problems.

While debugging, I found quite a few useful resources. There's [regexpal][] which I might work on in the holidays and [RegExr][]. [RegExr][] is more useful at the moment because it has the Replace functionality. I'll put it on the list of TODO / opensource stuff (along with Spritely) that I'll look into.

As a sidenote, [RegexInfo][] is indispensible as usual.

[regexpal]: http://regexpal.com/ 
[RegExr]: http://gskinner.com/RegExr/
[regexinfo]: http://www.regular-expressions.info/
