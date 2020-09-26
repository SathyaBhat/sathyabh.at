---
title: Upgrading to iPhone 3G to iPhone OS 3.1.2, with keeping the baseband at 04.26
author: sathya
type: post
date: 2010-03-30T02:33:28+00:00
url: /2010/03/30/upgrading-to-iphone-3g-to-iphone-os-3-1-2-with-keeping-the-baseband-at-04-26/




categories:
  - Mobiles
tags:
  - iPhone
  - jailbreak


---
I think this is my first post on iPhone ( barring the [rant][1]). o_O. Surprising, since I purchased the iPhone from eBay close to a year ago. Anyhow, being the computer <span style="text-decoration: line-through;">freak</span> enthusiast that I am,  I keep a track of most of the latest software that appears on the tech scene.  I generally have a zero-day update policy - any new version/update that arrives for a software I generally update it. I'm probably amongst the few folks who also read the release notes and change logs prior to upgrading, to find out if there's some new functionality or enhancement that has been added to the software which isn't so obvious. (Of course, some say if the new feature [isn't obvious in the UI][2], it is unlikely to get noticed, to which I agree. That said, do read the release notes. It will contain some good information). With the iPhone purchased, however I had to break this habit.

<!--more-->The core reason being - the iPhone's carrier lockdown. Its pretty known that the iPhone is carrier locked - which would mean that you cannot just pop in any random SIM and it would start working. There are, of course, 

[ways around this][3] thanks to some amazing efforts by bunch of [zomg-awesome folks][4].

The little side effects of this meant that I have to be extra careful whenever I use iTunes for fear of updating the iPhone firmware to the latest version - instantly losing the unlocks achieved and turning my iPhone into an iPod Touch with a mobile phone antenna that cannot be used 😐

There's a saying which goes with folks who use unlocked iPhones - if it works fine DO NOT UPGRADE! So then, why did I take the plunge and upgrade to the newer version ?

Couple of reasons:

  * Some of the newer apps - eg, the Digg app, Grand Theft Auto: Chinatown Wars, and some more that I purchased ( can't recall the names) require iPhone OS 3.1.2 atleast. This wasn't the primary reason, however.
  * My iPhone had become tremendously slow and unresponsive. So much so that 4 of the 10 calls that I receive would result in the iPhone freezing up, not responding to "Answer"  for about 10-15 seconds. 10-15 seconds may not seem a lot but when it comes to phone calls, a delay of even 5 seconds would indicate that the person is not available would result in missed calls, and considering my calls to my iPhone are most when I'm at work, and I get incoming ISD calls that I cannot call back from my phone - this was the most concerning part.

There's no doubt that the random lockups and freezes were due to the various software that I had installed from Cydia - these often run in the background( example [1][5], [2][6], [3][7], [4][8], [5][9], [6][10], [7][11] ) causing resource starvation and lockups.

Taking into consideration the above factors, I decided to take a backup, wipe my iPhone clean, upgrade to 3.1.2, jailbreak & get it unlocked again. However, I could not just grab the 3.1.2 firmware and upgrade it right away - reason being - baseband updates.

Baseband is the part of the iPhone which controls the telephony and other communication functions, and is an independent system from the iPhone OS which controls the apps. When I purchased the iPhone, the baseband was at 04.26.08 ("04.26") version, and I had no intention for the baseband to get updated with the newer version - reason being the 04.26 baseband has the most number of options of carrier unlocks. I wanted to upgrade the iPhone OS to 3.1.2, without touching the baseband. This was possible by getting my hands on the custom firmware created using Pwnage tool ( more details at [RedmondPie][12] ). Now with the firmware ready with me, I proceeded with updating my iPhone. Before starting the update, I took a final backup, noted down some important stuff ( read: office mail settings). Next, I hit shift, and clicked on the restore button, pointed to the custom .ipsw file and had my fingers crossed. The update went fine, but the RedmondPie article had me confused and a little concerned, since the article mentions

> After the installation is done, iPhone will restart automatically and you should now have a fully jailbroken iPhone running on firmware 3.1.2.

which was not true in my case. The iPhone screen was showing the connect to iTunes icon.

I was uncertain at this point, then realized, the phone was not jailbroken. So next went over to download [redsn0w][13]. Once downloaded, launched it, pointed it to the ipsw file and it did its thingamijig and \*ta-dah\*  the iPhone came alive, jailbroken, and confirmed it was still on [04.26][14]


Next step was to install ultrasn0w - which was pretty easy, just went over to Cydia and installed it. Rebooted, and [my carrier was recognised][15]. Finally, all that remained was restoring my backup. That was even easier, since the moment I launched iTunes, it prompted me, asking if I wanted to restore from my previous backup. Gave the affirmative choice and - about half hour later, my iPhone was ready - with all settings intact ( heh, including the battery percentage meter on the status bar and my office mail settings!).

The whole process took about  2 hours, but it was worth it, as now my iPhone is noticeably faster!

 [1]: ../2010/02/23/get-your-iphone-in-india-for-99-rs-4500-only/
 [2]: https://www.codinghorror.com/blog/2009/01/if-you-dont-change-the-ui-nobody-notices.html
 [3]: https://www.google.com/search?q=unlocking+the+iPhone&ie=utf-8&oe=utf-8&aq=t&rls=org.mozilla:en-US:official&client=firefox-a
 [4]: https://wikee.iphwn.org/
 [5]: https://twitpic.com/1872m3
 [6]: https://twitpic.com/16gox7
 [7]: https://twitpic.com/13o1t6
 [8]: https://twitpic.com/123vgp
 [9]: https://twitpic.com/11384o
 [10]: https://twitpic.com/vwxn2
 [11]: https://twitpic.com/9v70o
 [12]: https://www.redmondpie.com/jailbreak-and-unlock-iphone-3.1.2-firmware-on-windows-anu759/
 [13]: https://wikee.iphwn.org/howto:rs9
 [14]: https://twitter.com/SathyaBhat/status/11183955041
 [15]: https://twitter.com/SathyaBhat/status/11184177123
