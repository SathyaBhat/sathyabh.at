+++
author = "Sathyajith Bhat"
categories = ["Life"]
date = 2023-02-12T12:00:00Z
description = "Week 6 summary - Automated backups, beach visit and more..."
featured_image = "https://i.sathyabh.at/sb/weekly-notes/macquarie-lighthouse-2.jpg"
meta_image = "https://i.sathyabh.at/sb/weekly-notes/macquarie-lighthouse-2.jpg"
tags = ["weekly-notes", "sydney", "beach"]
title = "Weekly notes 06/2023"
type = "post"
url = "/2023/02/12/weekly-notes-06-2023/"
series = ["Weekly notes"]
+++

Since last week's [Red Hot Chili Peppers with Post Malone concert](/2023/02/04/red-hot-chili-peppers-post-malone-sydney-2023), I've been listening to a lot of Post Malone and Sunflower has been my earworm. It was apparently featured in the Spiderman: In to the Spiderverse movie, something I realized only after watching the music video (haven't seen any Spiderman movies since the second? idk, been far too long). Anyway, give it a [listen](https://www.youtube.com/watch?v=ApXoWvfEYVU). I found it quite catchy.

{{< youtube ApXoWvfEYVU >}}

### What's been happening

* Since I [bought my NAS](/2023/01/21/asustor-lockerstor4-as6604t/), I've been doing research on my backup strategies and what tools to look at. For moving data from the NAS to Cloud, I selected [restic](https://restic.net/) as my tool of choice, with it transferring the files to a S3 bucket. The bigger problem was continuously backing up data from my various devices (my desktop, Jo's desktop) to the NAS. Initially I had setup rsync but having to run rsync on a scheduled basis on my Windows systems was slightly annoying and I didn't want to run that manually. While doing some more research, I realized I could use [Syncthing](https://syncthing.net/). The Asustor NAS's OS, ADM, comes with Syncthing packaged, running in Docker with the mount points set up correctly, so all I had to do was setup Syncthing on Jo's and my PC and in a snap (and hours of syncing later), all of our data was sync'd over to the NAS and restic would do the backup. I still need to figure out how to get the photos from iCloud, but that's for later.
* I love Mangoes and missed them terribly while in Romania. The couple of times I bought them, I realized how poor they were in comparison to what I was used to. The mangoes were too hard, not sweet and yet everyone there seems loved the mangoes there. Wish I could show them how sweet the Indian Mangoes are. Moving to Sydney, it was the same problem - we tried different varities of mangoes - Calypso, Kensington Pride and one or two others and they were all pretty poor. Shout out to [Ooomz](https://twitter.com/ooomz/status/1612255745004957696) for the tip about Honey Gold which have been the best and the sweetest of the lot. As of last week, we've only seen the Keitt mangoes - these are the last mangoes of the season and I will have to wait for the next season. 
* Beach visit again yesterday! Initially went to [Camp Cove beach](https://goo.gl/maps/NroqmGhHfHweCLtA8) thinking it won't be crowded but many others had the same thought - we reached there and couldn't find parking, even after going around 3 times. We decided to go elsewhere and visited [Macquarie Lighthouse - Australia's first lighthouse](https://www.harbourtrust.gov.au/en/see-and-do/visit/macquarie-lightstation/). The views were gorgeous! The lighthouse itself was closed, but we went for a nice walk

  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "macquarie-lighthouse-1.jpg" "Macquarie Lighthouse" "Macquarie Lighthouse" >}}
  {{< fancybox "https://i.sathyabh.at/sb/weekly-notes" "macquarie-lighthouse-2.jpg" "Macquarie Lighthouse" "Macquarie Lighthouse" >}}

* From there we went over to Bondi beach, as that was the closest. Thankfully, we got a decent parking spot and I did a reverse-diagnol parking in my first shot!

  <iframe src="https://mastodon.social/@Sathyabhat/109846073990289490/embed" class="mastodon-embed" style="max-width: 100%; border: 0" width="400" allowfullscreen="allowfullscreen"></iframe><script src="https://static-cdn.mastodon.social/embed.js" async="async"></script>

  Here's some pics from the beach

  <iframe src="https://pxl.mx/p/sathyabhat/530178263158755829/embed?caption=true&likes=false&layout=full" class="pixelfed__embed" style="max-width: 100%; border: 0" width="400" allowfullscreen="allowfullscreen"></iframe><script async defer src="https://pxl.mx/embed.js"></script>

### Link of the week

Ever since Elon took over Twitter, I've been reducing using it quite a bit and increase my Fediverse presence(I'm on Maston at [@sathyabhat@mastodon.social](https://mastodon.social/@Sathyabhat)). I've been running my [own Pixelfed](https://pxl.mx/@sathyabhat) instance since over a year and half, but running a Mastodon server for friends and family is significantly more challenging. Most of the Fediverse apps are designed to be monoliths, run on beefy systems and maintaining them can be challenging. Cloudflare wrote up about [Wildebeest](https://blog.cloudflare.com/welcome-to-wildebeest-the-fediverse-on-cloudflare/), an open-source ActivityPub and Mastodon-compatible server built on top of their serves. I haven't given this a spin, but it shouldn't cost too much to run. Would have been nice if Cloudflare Images had a free tier, thereby making it possible to host ActivityPub/Mastodon server for small groups for free. For now, you'll have to pay $5 to subscribe to Cloudflare images. Give it a view.

That's for this week. See you next week.