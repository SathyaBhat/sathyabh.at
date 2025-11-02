+++
author = "Sathyajith Bhat"
categories = ["Life"]
tags = ["weekly-notes", "gaming"]
places = "Sydney"
type = "post"
series = ["Weekly notes"]
url = "/weekly-notes-44-2025/"
title = "Weekly notes 44/2025"
date = 2025-11-01T12:00:00Z
summary = "Week 44 summary - Cooling weather, house inspections, audiobook and more"
images = ["/weekly-notes-44-2025/thumb-.jpg"]

+++

![](thumb-.jpg)

_Thumbnail image: ._

### What's been happening

After couple of weeks of some really hot weather, Sydney has finally cooled down a bit with some rain and lower temperatures. It feels nice to have some cooler weather again. It was nice till the weekend came - we had some more house inspections planned for Saturday and rain played spoilsport. Thankfully, it was just light rain and we could still go ahead with the inspections. Carrying the umbrella definitely helped. It wasn't just the weather though - there was some track work planned for the weekend which meant that no Metro running along the North West route. There were train replacement buses, but we wanted to skip them as it takes a bit longer than the express buses. It's only been a year and half since the Metro extension to the city opened up and we've taken it for granted already! No metro meant that travel to Parklea/Stanhope Gardens area took a lot longer as we had to go to the city via train and then catch an express bus back from the city to Stanhope Gardens.

If those were not enough hassles, Jo dropped her iPad on her foot on Thursday evening. She was really struggling to walk on it on Friday, enough to get her to skip going into work. She's doing much better now but it's still a bit swollen and has been hobbling around, especially when walking along to the inspections. To add to this, I've been on-call this week at work which meant that I had to be available just in case something came up. Initially I thought of staying back home to be available, but with Jo not being able to walk properly, I decided to go along with her to the inspections. Thankfully, nothing major came up and I could focus on the house hunting.

Apart from these, it's been pretty quiet week. I noticed we had a whole bunch of CloudWatch Log groups in our AWS account that were not being used anymore. I wanted to estimate how much these would cost, so I refactored my previously written ec2-exporter to expand CloudWatch Logs as well. I also included a cost estimate and tags (if any) so I could see what I could remove that would yield the maximum savings. With this report (which runs in most of our regions), I was able to identify a few log groups that were not needed anymore and could be deleted. I'll work on expanding to a few other services as well in the coming weeks.

With Saturday and Sunday being busy with house inspections, we didn't get much time to relax. I knew with the Metro not being available, the bus ride would take a while so I wanted something apart from music. I'd subscribed to Audible a while back (Amazon was giving a 3-month subscription for a grand total of $1) and with these, I had 3 credits to buy audiobooks. Since Project Hail Mary was getting really good reviews, I decided to get that. I started listening to it on the bus rides and found it really engaging. I'm only about 4 chapters in, but I'm really enjoying it so far. The urge to find out what happens next is really strong, and I'm trying my best to not spoil it (a common trait that I have). 

### What I've been playing

Civilization VII - I continued my Genghis Khan campaign that I've been playing since the past few weeks. With my current science and culture production, I was able to research the required techs and civics to increase the settlement limit. The settlement limit is determined by the number of cities you have and the techs/civics you have researched> Going over this limit gives a happiness penalty, which can impact all your yields quite severely. With the new limit, I was able to conquer a few more cities from distant lands, giving me access to the treasure fleets that I can use to boost my economy and progress towards economic golden age. Genghis Khan's boost to military conquests combined with Mongolia's unique unit (Keshig) makes it really easy to conquer cities. The Keshig is a mounted archer with some great firepower and allows for some powerful hits. I'm getting towards the end of exploration era and looking forward to see how it ends and what Civ I can play for the Modern era.

Path of Exile - The new season on Path of Exile starts this weekend. I've previuously trying to get into the game multiple time but never got into it. My mistake last time was trying to play a build that was universally recommended (Poxh's Righteous Fire build). The build was pretty capable but was incredibly boring as you just walk around. This might be good for the 'blasters' who're trying to get as much currency as possible to flip/for the crafts but as a new player this left a pretty miserable taste for me. The service was also pretty poor with us having to call them out multiple times, and this with the restaurant mostly empty. I'm not sure what build I will try yet but knowing my affinity it will likely be spell-based.

### What we ate

[The Butcher's Block, Barangaroo](https://maps.app.goo.gl/wHojuscQFRoj9dNS6) - We went to this steakhouse earlier in the week along with my team mates. Given the location, we were quite excited to visit this place. But unfortunately it was a dud. We ordered some wings and ribs for starters which were pretty ok. For the main steak, all of us ordered the Wagyu Striploin and unfortunately the steak was pretty poorly done. I'd ordered medium-rare but it was closer to well done. The steak was also underseasoned. For sauce, I selected the green peppercorn cream which was pretty good. However, with the disappointing steak, I won't be recommending this place to anyone.

[Haveli, Stanhope Gardens](https://maps.app.goo.gl/h1qYVq4EE47oWxdN7) - We went to this Indian restaurant on Saturday after the house inspections. This is one of the few Indian restaurants in the area and we wanted to see how it fares. We ordered some sev puri, tandoori roti and bhuna lamb. The food was pretty okay, nothing great. The place we went to last week was much better. Probably worth visiting again to see if they do better as the menu was pretty expansive. 

[Gelateria Gondola Chatswood](https://maps.app.goo.gl/Qx9bcGPg3vs6pFi16) - A small quaint little gelato place in Chatswood. We went here on Sunday after the house inspections. Jo had previously been here and she was raving about it, I figured would be a good treat for our 16k steps + 9k steps for the weekend. It's pretty easy to miss this place but once you walk in you realize they have a variety of gelato flavours. I had the pistachio and dmint/chocolate while Jo had the hazelnut and vanilla. The gelato was indeed really good. The texture was rich and creamy and it wasn't too sweet either. Glad to find a good gelato place!

### Music of the Week

Playing Civ 7 reminds me how much effort they put into to the themes for all the civilizations. Here is Mongolia's theme from Civ 7 which is really [good](https://www.youtube.com/watch?v=9zKKD3ctH1M)

{{< youtube 9zKKD3ctH1M >}}

And for good measure, here is Mongolia's [theme from Civ 6](https://www.youtube.com/watch?v=u14DMxPNek4) as well:

{{< youtube u14DMxPNek4 >}}

### Link of the week

[Rushabh Vora](https://mastodon.social/@rushvora@hachyderm.io) shared this great video from Coffeezilla about the gambling epidemic. It's a long 34-minute video but well worth watching. Both Romania and Australia have pretty lax gambling laws which has led to a lot of people getting addicted to gambling. In Sydney CBD, you'll find these "VIP" rooms in almost every pub around the nook which are just nothing but gambling dens. In Romania it was so common to see gambling ads everywhere (TV/physical) and lot of places where people would just gamble away, it was insane. Go [check out the video](https://www.youtube.com/watch?v=9Ii1ROzeSwU) to see how bad it can get.

{{< youtube  9Ii1ROzeSwU >}}

### Thanks for reading.

Thanks for reading and have a great week ahead.

Subscribe to my weekly notes:

- [Email newsletter](https://sathyabhat.substack.com/)
- [RSS feed for the weekly notes](https://sathyabh.at/series/weekly-notes/index.xml)
- [RSS feed for my site](https://sathyabh.at/index.xml)
