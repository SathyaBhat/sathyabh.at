---
title: Websense redirect – My First Chrome Extension
author: sathya
type: post
date: 2011-02-04T10:35:11+00:00
url: /2011/02/04/websense-redirect-my-first-chrome-extension/


arkayne-time-post:
  - "1325785815"
categories:
  - Programming
tags:
  - Chrome
  - Extension
  - extensions
  - Google Chrome
  - Google Chrome Extension
  - javascript
  - webnonsense

---
At my (current) workplace we have a webfiltering mechanism powered by [WebSense][1]. I've [ranted][2] enough number of times on twitter about websense's [stupid][3] filtering mechanisms & the [bizarre][4] [classification][5] that it uses to [classify websites][6].  
<!--more-->

  
Recently, I found that fetching the mobile(aka text-only) versions of webpages using instapaper/google web transcoder would result in me being able to read the content - which was a very nice alternative because majority of the time, I'd be reading up on posts which are text heavy in nature. It was getting irritating to open to a webpage, encounter a blocked page, open another tab & copy-paste the URL to instapaper to grab the text version. I [asked my peers][7] are [Super User][8]:

> is there a ModRewrite-like extension for chrome ? :-s

[TomWij][9] pointed me towards Privoxy but that was not what I needed. So I decided to build a Chrome Extension. The first version of the extension I built fairly quickly, but required manual intervention by way of clicking on the Extension icon to trigger the redirect - clearly not an ideal solution. Taking a deeper look at Chrome Extension API docs, I realized that I needed to build a [content script][10].

Building up on this - I created a simple extension which checks for websense blocking pattern and if so - redirects it to instapaper which then fetches the text-only version. While this extension is not really the best-thing-since-sliced-bread, it's of immense use to me. (And of course, I learnt to build a Chrome Extension, which I always wanted to do).

There are certain bugs, but I can live with those for the moment. If you need a similar thing - do try out my extension &#8212; it's hosted on my servers & can be downloaded from over [here][11]. Let me know if you run into problems.

 [1]: https://www.websense.com/content/home.aspx
 [2]: https://twitoaster.com/country-in/sathyabhat/congrats-reddit-you-have-now-been-promoted-to-the-rank-of-a-social-network-by-webnonsense/
 [3]: twitter.com/SathyaBhat/statuses/28059352136945664
 [4]: https://tumble.sathyabh.at/post/587335342/more-webnonsense-stupidity
 [5]: ttp://friendfeed.com/100rabh/1cec68cc/rt-sathyabhat-all-hail-web-non-sense-says-hacker
 [6]: https://tumble.sathyabh.at/post/49820040/web-non-sense
 [7]: https://chat.stackexchange.com/transcript/118?m=437454#437454
 [8]: https://superuser.com/users/4377/sathya
 [9]: https://superuser.com/users/9666/tomwij
 [10]: https://code.google.com/chrome/extensions/content_scripts.html
 [11]: https://u.sbhat.me/webnonsense
