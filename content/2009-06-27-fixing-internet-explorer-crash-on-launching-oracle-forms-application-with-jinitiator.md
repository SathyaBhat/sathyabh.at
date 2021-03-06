---
title: Fixing Internet Explorer Crash on Launching Oracle Forms Application with jInitiator
author: Sathyajith Bhat
type: post
date: 2009-06-26T21:29:20+00:00
url: /2009/06/27/fixing-internet-explorer-crash-on-launching-oracle-forms-application-with-jinitiator/

categories:
  - 'Oracle & PL/SQL Stuff'
tags:
  - Internet Explorer
  - jinitiator

---
I've been facing this really annoying problem for quite some time now. My job revolves around developing apps using [Oracle Forms Builder][1]. Oracle Forms applications, uses Java applets to run inside any browser, on most platforms. Here's the kink - Oracle Forms applications by default uses [Oracle's][2] [jInitiator][3] which is a JVM made by Oracle and allows a web enabled <a style="text-decoration: none; background-image: none; background-repeat: initial; background-attachment: initial; -webkit-background-clip: initial; -webkit-background-origin: initial; background-color: initial; color: #5a3696; background-position: initial initial;" title="Oracle Forms" href="https://en.wikipedia.org/wiki/Oracle_Forms">Oracle Forms</a> client application to be run inside a web browser.

As much as I hate using Internet Explorer - I have to depend on it as the my app depends on other components which are designed on run on Internet Explorer only 😐 

Till now I've been using Mozilla Firefox, but now the situation demands that I needed to use Internet Explorer. And when I launched Internet Explorer - Ka boom! Internet Explorer crashes. Did few things, such as disabling all addons, getting rid of Sun's JVM et al, but made no difference.



Finally, I came across a solution(or rather a workaround) - replace the jvm.dll in jinitiator directory with that present in Sun's JRE 1.6. If you don't want to install the whole bundle - just [click here][4](jvm.dll, 2.2 MB), I've uploaded just the jvm.dll file, rename the original jvm.dll (present in jinitiator/bin/hotspot directory) to, say jvm.dll.old, and replace it with the one given in the above link. Restart the browser, IE shouldn't crash anymore.

 [1]: https://en.wikipedia.org/wiki/Oracle%20Forms
 [2]: https://en.wikipedia.org/wiki/Oracle%20Corporation
 [3]: https://en.wikipedia.org/wiki/Jinitiator
 [4]: https://files.getdropbox.com/u/3353/jvm.dll
