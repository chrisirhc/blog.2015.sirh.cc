---
layout: post
title: Push notifications on Android
---

Update\: This article is outdated and is kept here for archival purposes.
It seems that all these projects have been killed by the push notification APIs that Apple and Google have created for their respective mobile operating systems.

### [Ericsson Mobile Push][ericsson]

Uses SMS for push notification.
This makes it less of a real-time tool, because it usually takes about 10 seconds on average for a notification to be pushed into my phone.
However, it be dead simple for creating notifications.
I used X4S to send out the XML requests. It uses XML-RPC to handle the requests.

### [Extify][]

Does not require setting up of a server.
Allows you to keep track of the users that use your service. This could be a good or bad thing depending on how you look at it.
Personally, I find it rather creepy that it keeps track of the user's location even when the user is no longer using your application.
However, this is useful if you are creating an application that sends notifications to the server when the user is near certain locations. Extify has these under its campaign options.

### [MQTT][]

Fast communication.  
Requires setting up a server.  
Java or [PHP SAM][php_sam] is probably the only way to connect and communicate with MQTT.

I know it feels a little like comparing apples with oranges but this really is a viable solution.
I really do hope that the licensing issues do get cleaned up and we can have a version that we setup a broker instance on Google Apps Engine or the like. (I'm not sure how that works, I'm just talking about the possibilities since running it on my home server isn't a production solution)

Limitations: Claims to be able to handle up to 3000 clients simultaneously.

### Comet

[Persvr][persvr] looks good

### XMPP

So far, from what I see, it seems rather complicated to setup XMPP.

[ericsson]:#https://labs.ericsson.com/apis/mobile-push/ "Mobile Push"
[extify]: #http://extify.com "Extify"
[mqtt]: #http://mqtt.com "MQTT"
[php_sam]: #http://php.net/manual/en/book.sam.php "PHP SAM"
[persvr]: http://persvr.org/ "Persevere"
