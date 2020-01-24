---
title: Fixing Internet Explorer Crash on Launching Oracle Forms Application with jInitiator
author: sathya
type: post
date: 2009-06-26T21:29:20+00:00
url: /2009/06/27/fixing-internet-explorer-crash-on-launching-oracle-forms-application-with-jinitiator/
aktt_notify_twitter:
  - 'no'

arkayne-time-post:
  - "1325792094"
categories:
  - 'Oracle &amp; PL/SQL Stuff'
  - Programming
tags:
  - Forms
  - IE
  - Internet Explorer
  - jinitiator
  - oracle

---
I&#8217;ve been facing this really annoying problem for quite some time now. My job revolves around developing apps using [Oracle Forms Builder][1]{#aptureLink_dzpThUVtnA}. Oracle Forms applications, uses Java applets to run inside any browser, on most platforms. Here&#8217;s the kink &#8211; Oracle Forms applications by default uses [Oracle&#8217;s][2]{#aptureLink_5VcUe7aCHj} [jInitiator][3]{#aptureLink_uyXnIMpqB7} which is a JVM made by Oracle and allows a web enabled <a style="text-decoration: none; background-image: none; background-repeat: initial; background-attachment: initial; -webkit-background-clip: initial; -webkit-background-origin: initial; background-color: initial; color: #5a3696; background-position: initial initial;" title="Oracle Forms" href="https://en.wikipedia.org/wiki/Oracle_Forms">Oracle Forms</a> client application to be run inside a web browser.

As much as I hate using Internet Explorer &#8211; I have to depend on it as the my app depends on other components which are designed on run on Internet Explorer only 😐 

Till now I&#8217;ve been using Mozilla Firefox, but now the situation demands that I needed to use Internet Explorer. And when I launched Internet Explorer &#8211; Ka boom! Internet Explorer crashes. Did few things, such as disabling all addons, getting rid of Sun&#8217;s JVM et al, but made no difference.

[ad]

Finally, I came across a solution(or rather a workaround) &#8211; replace the jvm.dll in jinitiator directory with that present in Sun&#8217;s JRE 1.6. If you don&#8217;t want to install the whole bundle &#8211; just [click here][4]{#aptureLink_xEBjE1aaLa}(jvm.dll, 2.2 MB), I&#8217;ve uploaded just the jvm.dll file, rename the original jvm.dll (present in jinitiator/bin/hotspot directory) to, say jvm.dll.old, and replace it with the one given in the above link. Restart the browser, IE shouldn&#8217;t crash anymore.

 [1]: https://en.wikipedia.org/wiki/Oracle%20Forms
 [2]: https://en.wikipedia.org/wiki/Oracle%20Corporation
 [3]: https://en.wikipedia.org/wiki/Jinitiator
 [4]: https://files.getdropbox.com/u/3353/jvm.dll
