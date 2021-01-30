---
title: Of Z-Wave, SmartThings, Amazon Echo, Google Home, Kwikset Deadbolt and the colossal failure that is connecting them all – aka “Home Automation”
author: Sathyajith Bhat
type: post
date: 2017-12-29T11:51:49+00:00
url: /2017/12/29/of-z-wave-smartthings-amazon-echo-google-home-kwikset-deadbolt-and-the-colossal-failure-that-is-connecting-them-all-aka-home-automation/
categories:
  - Computing
tags:
  - alexa
  - epic fail
  - fail
  - google assistant
  - home automation
  - kiwkset
  - smartthings hub

---
This is a huge rant I sent to [Jo][1]. Some backstory: Few months back Jo bought a <a href="https://www.amazon.com/Kwikset-SmartCode-Electronic-SmartThings-featuring/dp/B004F1B24I/ref=sr_1_1?ie=UTF8&qid=1514550037&sr=8-1&keywords=kwikset+910" target="_blank" rel="noopener">Kwikset 910 deadbolt</a> (more like I asked her to buy - hindsight I should have done more and better research) and I was trying to setup the remote locking feature using Alexa/Google Assistant via <a href="https://www.amazon.com/Samsung-SmartThings-Smart-Home-Hub/dp/B010NZV0GE/ref=sr_1_3?s=hi&ie=UTF8&qid=1514550067&sr=1-3&keywords=smartthings+hub" target="_blank" rel="noopener">SmartThings</a> Hub. Here's a copy-paste of the entire message. I'll have a separate post on my home automation setup.

<!--more-->

> Sathya Bhat, [29.12.17 16:25]  
> well that was a completely wasted afternoon
> 
> Jo Shenoy, [29.12.17 16:25]  
> ?
> 
> Sathya Bhat, [29.12.17 16:25]  
> first spend an hour trying to find the screw driver
> 
> Sathya Bhat, [29.12.17 16:25]  
> then find the screw driver
> 
> Sathya Bhat, [29.12.17 16:25]  
> unlock the deadbolt
> 
> Sathya Bhat, [29.12.17 16:25]  
> put the deadbolt in pairing mode.
> 
> Sathya Bhat, [29.12.17 16:26]  
> deadbolt doesn't get detected by smartthings
> 
> Sathya Bhat, [29.12.17 16:26]  
> help says keep hub near 10-15 feet of deadbolt
> 
> Sathya Bhat, [29.12.17 16:26]  
> fine
> 
> Sathya Bhat, [29.12.17 16:26]  
> move the hub
> 
> Sathya Bhat, [29.12.17 16:26]  
> Hub's battery powered, so no problem right
> 
> Sathya Bhat, [29.12.17 16:26]  
> wrong
> 
> Sathya Bhat, [29.12.17 16:26]  
> hub needs Internet
> 
> Sathya Bhat, [29.12.17 16:26]  
> and the hub is moved to the hall
> 
> Sathya Bhat, [29.12.17 16:26]  
> how do I get Internet to the hall
> 
> Sathya Bhat, [29.12.17 16:27]  
> rummage around
> 
> Sathya Bhat, [29.12.17 16:27]  
> find a \_looooong\_ Ethernet cable
> 
> Sathya Bhat, [29.12.17 16:27]  
> drag the cable to the wrong
> 
> Sathya Bhat, [29.12.17 16:27]  
> > still not detected
> 
> Sathya Bhat, [29.12.17 16:27]  
> google more
> 
> Sathya Bhat, [29.12.17 16:27]  
> one result says try excluding device first
> 
> Sathya Bhat, [29.12.17 16:27]  
> but what to exclude when it's not included?!?
> 
> Sathya Bhat, [29.12.17 16:28]  
> ok, no harm in trying
> 
> Sathya Bhat, [29.12.17 16:28]  
> find out how to exclude
> 
> Sathya Bhat, [29.12.17 16:28]  
> surprise, surprise, exclusion mode is stuck deep in the app
> 
> Sathya Bhat, [29.12.17 16:28]  
> somehow find it
> 
> Sathya Bhat, [29.12.17 16:28]  
> press button on deadlock
> 
> Sathya Bhat, [29.12.17 16:28]  
> yay exclusion successful
> 
> Sathya Bhat, [29.12.17 16:28]  
> try pairing
> 
> Sathya Bhat, [29.12.17 16:28]  
> nervous moments
> 
> Sathya Bhat, [29.12.17 16:29]  
> yay pairing succeeded
> 
> Sathya Bhat, [29.12.17 16:29]  
> lock seen by smartthings app
> 
> Sathya Bhat, [29.12.17 16:29]  
> press the unlock button
> 
> Sathya Bhat, [29.12.17 16:29]  
> it works!
> 
> Sathya Bhat, [29.12.17 16:29]  
> hahahha
> 
> Sathya Bhat, [29.12.17 16:29]  
> door unlocked
> 
> Jo Shenoy, [29.12.17 16:29]  
> then?
> 
> Sathya Bhat, [29.12.17 16:29]  
> lets try automating
> 
> Sathya Bhat, [29.12.17 16:29]  
> > Alexa: lolyeahsure, not in India man
> 
> Jo Shenoy, [29.12.17 16:29]  
> [In reply to Sathya Bhat]  
> &#x1f602;
> 
> Sathya Bhat, [29.12.17 16:29]  
> > google home: wut is this lock thing? I know only on and off lights
> 
> Sathya Bhat, [29.12.17 16:29]  
> ok
> 
> Sathya Bhat, [29.12.17 16:30]  
> lets try unlinking and relinking the smartthings app
> 
> Sathya Bhat, [29.12.17 16:30]  
> maybe it needs to be refreshed
> 
> Sathya Bhat, [29.12.17 16:30]  
> ok, unlinked and relinked
> 
> Sathya Bhat, [29.12.17 16:30]  
> > smartthings seen
> 
> Sathya Bhat, [29.12.17 16:31]  
> > googlehome: yeahlolrite you think that works? this aint windoz man
> 
> Sathya Bhat, [29.12.17 16:31]  
> \_sigh\_
> 
> Sathya Bhat, [29.12.17 16:31]  
> Idea &#x1f329;
> 
> Sathya Bhat, [29.12.17 16:31]  
> lets try ifttt
> 
> Sathya Bhat, [29.12.17 16:31]  
> > launch ifttt
> 
> Sathya Bhat, [29.12.17 16:31]  
> connect smartthings
> 
> Sathya Bhat, [29.12.17 16:31]  
> connect google assistant
> 
> Sathya Bhat, [29.12.17 16:32]  
> put in ifttt: if you say "abracadabra" or "khul ja sim sim" or "open the door" tell smart things to unlock
> 
> Sathya Bhat, [29.12.17 16:32]  
> ok, done
> 
> Sathya Bhat, [29.12.17 16:32]  
> > say hey google from the hall
> 
> Sathya Bhat, [29.12.17 16:32]  
> > Google home from bedroom responds
> 
> Sathya Bhat, [29.12.17 16:32]  
> &#x1f926;
> 
> Sathya Bhat, [29.12.17 16:32]  
> try again with holding the homebutton on the phone
> 
> Sathya Bhat, [29.12.17 16:33]  
> google assistant responds on phone
> 
> Sathya Bhat, [29.12.17 16:33]  
> > say khul ja sim sim
> 
> Sathya Bhat, [29.12.17 16:33]  
> > google assistant: calling john simpson
> 
> Sathya Bhat, [29.12.17 16:33]  
> &#x1f926;&#x200d;
> 
> Sathya Bhat, [29.12.17 16:33]  
> try again
> 
> Sathya Bhat, [29.12.17 16:33]  
> > google assistant: calling john simpson
> 
> Sathya Bhat, [29.12.17 16:33]  
> fuck this shit
> 
> Sathya Bhat, [29.12.17 16:34]  
> > hey google, abracadabra
> 
> Sathya Bhat, [29.12.17 16:34]  
> holy fuck
> 
> Sathya Bhat, [29.12.17 16:34]  
> it works
> 
> Sathya Bhat, [29.12.17 16:34]  
> !!!!!
> 
> Sathya Bhat, [29.12.17 16:34]  
> door unlocked
> 
> Sathya Bhat, [29.12.17 16:34]  
> woohooo
> 
> Sathya Bhat, [29.12.17 16:34]  
> try again
> 
> Sathya Bhat, [29.12.17 16:34]  
> not a fluke
> 
> Sathya Bhat, [29.12.17 16:34]  
> happy with results
> 
> Sathya Bhat, [29.12.17 16:34]  
> put the cover on the deadbolt
> 
> Sathya Bhat, [29.12.17 16:34]  
> move smartthings hub back to bedroom
> 
> Sathya Bhat, [29.12.17 16:34]  
> stash in lan cable etc
> 
> Sathya Bhat, [29.12.17 16:35]  
> > lay down, automation: PROJECT SUCCESSFUL
> 
> Sathya Bhat, [29.12.17 16:35]  
> Dr Murphy: yeah lolright
> 
> Sathya Bhat, [29.12.17 16:35]  
> > hey google, abracadabra
> 
> Sathya Bhat, [29.12.17 16:35]  
> &#8230;.
> 
> Sathya Bhat, [29.12.17 16:35]  
> ifttt: yo bro, I sent the commandz but dunno brosky
> 
> Sathya Bhat, [29.12.17 16:36]  
> smartthings app: I dunno &#x1f937;&#x200d;
> 
> Sathya Bhat, [29.12.17 16:36]  
> > smartthings app: door locked
> 
> Sathya Bhat, [29.12.17 16:36]  
> > me open lock:
> 
> Sathya Bhat, [29.12.17 16:36]  
> smartthings: nopes, you're imagining shit. door still locked
> 
> Sathya Bhat, [29.12.17 16:36]  
> me: ok, since I disconnected the hub let me try to reconnect
> 
> Sathya Bhat, [29.12.17 16:37]  
> > find z-wave network repair deep in app
> 
> Sathya Bhat, [29.12.17 16:37]  
> > app: yo, yer deadbolt: seems to be lost, can't find it
> 
> Sathya Bhat, [29.12.17 16:37]  
> ok, let me do the exclusion
> 
> Sathya Bhat, [29.12.17 16:37]  
> can't exclude
> 
> Sathya Bhat, [29.12.17 16:37]  
> so yeah remember the 10-15ft thing
> 
> Sathya Bhat, [29.12.17 16:38]  
> eeyep smartthings hub needs to be close for the lock to work via app
> 
> Sathya Bhat, [29.12.17 16:38]  
> so yeah  
> 2.5 hours down the drain

&nbsp;

 [1]: https://twitter.com/joshenoy