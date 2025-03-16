+++
author = "Sathyajith Bhat"
categories = ["Life"]
tags = ["weekly-notes", "gaming"]
places = "Sydney"
type = "post"
series = ["Weekly notes"]
url = "/weekly-notes-<<week>>-2025/"
title = "Weekly notes <<week>>/2025"
# date = 2025-<<month>>-<<date>>T12:00:00Z
summary = "Week <<week>> summary"
images = ["/weekly-notes-<<week>>-2025/thumb-.jpg"]
+++

![](thumb-.jpg)

_Thumbnail image: ._

### What's been happening

It’s been a pretty terrible week. Work was a bit meh. After last week’s cloud cover, it’s been a hot and humid week here in Sydney. There’s a heatwave warning issued and even a fire ban for the weekend.

As I get older, I’m firmly moving away from my tinkering mindset into the “if it ain’t broken, don’t fix it” mindset.

I decided to install HomeAssistant on my [NAS](https://sathyabh.at/tag/nas). HomeAssistant comes with widgets and control center shortcuts - something that I was missing in Google Home and having to open Google Home app to turn off the lights is just too annoying. Usually I run apps on the NAS using Docker, not by installing the app using Asustor’s AppStore. Jo was preparing dinner and called me to help her, so I thought I’ll install HomeAssistant using Asustor’s AppStore. Well that was a bad choice - that install ended up upgrading the Docker engine which generally hasn’t been a problem thus far. This time, it wiped out all my running containers, custom networks, heck even the docker volumes. Thankfully I didn’t lose most data since I had configured all containers to use bind mounts instead of docker volumes. 

Some of the containers I was running didn’t have docker-compose files so had I had to recreate the containers. I use Portainer for the container management that was installed via the Asustor AppStore and the data from Portainer was also wiped out. In the end, I spent a couple of hours trying to get everything back together. So much for saving time. I did lose about a year’s worth of location history because [OwnTracks](https://sathyasays.com/2024/07/13/self-hosting-owntracks-google-maps-timeline-alternative/) was accidentally configured to use Docker Volumes instead of bind mount. Oh well, I might consider writing something to export data from Google Maps into OwnTracks at a later point.

There were a bunch of positives though. I’m back to my usual weights while doing lifts & squats at the gym. My back doesn’t have the niggle any more. I beat my PB when doing dumbbell bench press (17.5 kilos) and dumbbell shoulder press (12.5 kilos). We’re back to our guitar class and it was a bit of a tough one - we learnt and played [Smile](https://en.wikipedia.org/wiki/Smile_(Charlie_Chaplin_song)) - which is fair bit more technical and challenging than what we’ve done before. 

Post the guitar class, we went over to the fornightly North Sydney Produce market, picking up our usual staple groceries. We also met Jo’s friend who lives nearby and after the grocery shopping and dropping the produce back home, we went over to 63 degrees Cafe. After spending couple of hours at the cafe, we came back home to watch the Melbourne Grand Prix races. 

{{< fancybox "https://i.sathyabh.at/sb/weekly-notes" ".jpg" "" "Weekly Notes" >}}

### What I’ve been playing

Been another week of Path of Exile 2 for me. I’m very close to finishing the final Act but getting here was a huge slog. The map sizes are ridiculously large, lots of places where enemies overwhelm you, or champions stun-lock and one-shot you. When you die, you’re resurrected at the last checkpoint which so far hasn’t been a problem but given how long the maps are plus with the enemies overwhelming you, it’s been a real slog and in many ways a case of one step forward, two steps back. Here’s couple of boss fights 

{{< youtube lhLn7Rxs_uY >}}

{{< youtube Guq8ling1vc >}}

### What we watched

Wheel of Time, Season 3 - We started watching the previous season with a weird sense of Deja vu and me telling Jo “we've seen these episodes!” After a few minutes of trying to recall what exactly we should be watching, catching up on the events of season 2, we started watching the new season. After the first two episodes, I’m still quite confused about what the heck is happening. There’s a lot of fighting, bunch of spells, some merrymaking (!?) when they are supposed to remain hidden, a bunch of jibber-jabber dialogue, double/triple-crossing all makes for one very befuddled story telling. We’ll have to wait and watch and see how this progresses.

The Amazing Race, Season 37 - Second episode of Season 37 is pretty decent. The teams travel to Osaka, Japan where they take on choices of sumo wrestling or pounding rice to form mochi. The “intersection” forces teams to wait for second team and perform the task together. Overall, good watch and should be interesting to see how the race progresses.

### What we ate

[Sakura, North Sydney](https://maps.app.goo.gl/6ka7hR2dyvh8JydKA?g_st=com.google.maps.preview.copy) A nice little Japanese restaurant right next to Saravana Bhavana, Sakura’s got nice cozy interiors as well as some nice outdoor seating. We ordered some Sake and after seeing the size of the bottle we realized we made a big mistake. The food was really good - we ordered the Renkon chips, chicken roll for Jo and teriyaki wagyu stir fry for myself. After downing the entire bottle split among ourselves and somehow not managing to fall over, we went over to the Twilight Food Fair and grabbed couple of Salted Caramel & White Chocolate gelato!

### Music of the Week


### Link of the week

### Thanks for reading.

Thanks for reading and have a great week ahead.

Subscribe to my weekly notes:

- [Email newsletter](https://sathyabhat.substack.com/)
- [RSS feed for the weekly notes](https://sathyabh.at/series/weekly-notes/index.xml)
- [RSS feed for my site](https://sathyabh.at/index.xml)
