+++
author = "Sathyajith Bhat"
categories = ["Life"]
tags = ["weekly-notes", "gaming"]
places = "Sydney"
type = "post"
series = ["Weekly notes"]
url = "/weekly-notes-06-2025/"
title = "Weekly notes 06/2025"
date = 2025-02-08T12:00:00Z
summary = "Week 06 summary - one more turn..."
images = ["/weekly-notes-06-2025/thumb-art-gallery-nsw.jpg"]

+++

![](thumb-art-gallery-nsw.jpg)

_Thumbnail image: The Art Gallery of New South Wales is one of the largest in Australia._

### What's been happening

It's been a pretty warm week in Sydney. We've had 30+ degree temperatures all week. It was supposed to rain this weekend but it seems like the clouds were blown away. The heat makes it difficult to work/play in my office since the sunlight falls directly into the room and makes it hot pretty fast - to the extent that if I don't close the blinds before going to sleep, it's going to be an incredibly hot room to be in. Thankfully, we do have air-conditioning in the house, so that has made the heat bearable. The [Vornado whole room air circulator](/2023/01/21/weekly-notes-03-2023/) has been working overtime as well and has helped in keeping the overall temperatures in the house manageable.

Long ago, I had set up a WordPress site for [Justin](https://www.justinjaideep.in/). He reached out to me asking if I could help set up a new WordPress site and theme, revamping his old site. I have some free time now, so I decided to accept the work. I'll work on it soon over the next few days.

I'd been hearing a lot about [Cursor](https://www.cursor.com/), [Windsurf](https://codeium.com/windsurf) and other such AI editors and wanted to give them a spin. My current workflow for managing and uploading images for this blog has also been a pain since I use Hugo, a static site generator which works well for text. I figured this would be a perfect time to test out Cursor, and I used it to build a React webapp to upload images to the AWS S3 bucket where the weekly notes images are saved. My previous workflow for image edits was:

* Select the images
* Rename the image files using [PowerRename](https://learn.microsoft.com/en-us/windows/powertoys/powerrename)
* Resize the images using [IrfanView](https://www.irfanview.com/)
* Optimize the images using [jpegoptim](https://github.com/tjko/jpegoptim)
* Upload the images to S3 using AWS CLI

This is a fair number of steps, and I wanted to simplify this, so I started with a prompt describing my problem and what I wanted. After several prompt updates, I managed to get what I wanted. Sure, it's not the best UI, but it's pretty functional and saves a bunch of time for me. Pretty impressed with Cursor. It was not all smooth sailing - several times I had to rollback to earlier checkpoints (Cursor's way of tracking state of the application) because some of the changes I asked for resulted in too much regression. Here's a [Twitter thread with screenshots](https://x.com/SathyaBhat/status/1888082272794067148). Also, writing this reminds me that I've been using

{{< tweet sathyabhat 1888082272794067148 >}}

Meanwhile at work, I have taken up an extension to my current role as the Scrum Master for me team. I'll be working closer with my Engineering Manager, Product Manager and my fellow leads and help my team get better. Look forward to seeing how that goes.

On the weekend, I was mostly at home since I wanted to play Civilization VII. Jo went out to check out some opshops and record stores and came back with two records - one of Steppenwolf and the other Santana's Lotus album.

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "santana-lotus-250208-1.jpg" "Santana - Lotus" "Weekly Notes" >}}
  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "steppenwolf-live-250208-1.jpg" "Steppenwolf - Live" "Weekly Notes" >}}

### What I played

Civilization VII was available this week in advance access and I've been playing a whole lot of it. I've got three games going on - a solo game, two multiplayer games - one with Kush and other with Kush & Rushabh. Civilization VII brings a number of changes - the most upfront being in Civilization VII, you get to choose a leader and Civilization separately. At the end of an age, you get to choose a new civilization that you will assume so this brings in a lot of replayability and choices. Civilization VII's music is fantastic and really sets the mood for the game. If you look at the reviews, you'll see that the game has a "Mixed" rating - and that's because the game has a severe UI problem. There's a lot of broken things in Civilization VII - be it really bad UI placement, insufficient data being shown - feels like a UI that was thrown in early dev and never looked at. I hope this gets improved soon.

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "civ-7-250208-1.jpg" "Civilization VII" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "civ-7-250208-2.jpg" "Civilization VII" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "civ-7-250208-3.jpg" "Civilization VII" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "civ-7-250208-4.jpg" "Civilization VII" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "civ-7-250208-5.jpg" "Civilization VII" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "civ-7-250208-6.jpg" "Civilization VII" "Weekly Notes" >}}

### What we ate

Throughout the week, Jo had been wanting to eat Koli Saaru (Karnataka style chicken curry) and asked me to get chicken legs. Unfortunately both the grocery stores I went to didn't have chicken legs, only thighs (why is it that you can never find the item you most want?). Undeterred by this, she put in an Uber Eats order and got the chick legs (and other groceries, of course) delivered to home and spent a long time and finally made rice and Koli Saaru. It was delicious! Here's the [recipe](https://www.kannammacooks.com/karnataka-style-koli-saaru-kozhi-saaru-chicken-curry-recipe/) that Jo used. 

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "koli-saaru-250208-1.jpg" "Koli Saaru" "weekly notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "koli-saaru-250208-2.jpg" "Koli Saaru" "weekly notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "koli-saaru-250208-3.jpg" "Koli Saaru" "weekly notes" >}}

[Eighty Ate, North Sydney](https://maps.app.goo.gl/ZjHqhQTWTVX6eyEFA) Eighty Ate is a nice little coffee shop in North Sydney. I thought we've been here couple of times already but seems like the the last time I visited was about a year ago. I had corn fritters with a poached egg while Jo had a Patatas bravas. The food was pretty good, coffee wasn't bad either. The corn fritters got a bit tedious to eat since it was a bit dry. Still would recommend them for their pancakes!

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "eighty-ate-250208-1.jpg" "Eighty Ate" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "eighty-ate-250208-2.jpg" "Eighty Ate" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "eighty-ate-250208-3.jpg" "Eighty Ate" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "eighty-ate-250208-4.jpg" "Eighty Ate" "Weekly Notes" >}}

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "eighty-ate-250208-5.jpg" "Eighty Ate" "Weekly Notes" >}}

### Music of the Week

King Stingray is an Australian rock band from the Northern Territory and they did a really good version of Coldplay's Yellow. I can't wait to catch them live soon

{{< youtube sr3iI8gg2fo >}}

### Link of the week

I came across this post which talks about how they made Gorillaz' videos. It's bit of [a long read](https://animationobsessive.substack.com/p/making-the-video-that-made-gorillaz) so grab something to drink/eat

### Thanks for reading.

Thanks for reading and have a great week ahead.

Subscribe to my weekly notes:

- [Email newsletter](https://sathyabhat.substack.com/)
- [RSS feed for the weekly notes](https://sathyabh.at/series/weekly-notes/index.xml)
- [RSS feed for my site](https://sathyabh.at/index.xml)
