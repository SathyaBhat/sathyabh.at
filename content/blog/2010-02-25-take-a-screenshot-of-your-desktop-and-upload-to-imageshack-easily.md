---
title: Take a screenshot of your desktop and upload to ImageShack imgur easily
author: sathya
type: post
date: 2010-02-25T01:28:04+00:00
url: /2010/02/25/take-a-screenshot-of-your-desktop-and-upload-to-imageshack-easily/


arkayne-time-post:
  - "1325778409"
categories:
  - Programming
tags:
  - .net
  - imageshack
  - imageshack uploader
  - Programming
  - uploader

---
I wanted a simple tool to upload to Imageshack with minimum fuss and absolutely no config settings, couldn&#8217;t find any such so I built one myself.  Just extract all the files to a folder, run the executable, and if you want to upload something to  Imageshack, hit PrintScreen and double click the icon on the system tray, it&#8217;ll automatically upload to <s>ImageShack</s> imgur, and once upload is done, will give you a notification and copy the <s>ImageShack</s> imgur URL to the clipboard.

<!--more-->

  
I&#8217;ve been using this for the past few <span style="text-decoration: line-through;">weeks</span> months now, and seems to work fine atleast on Win 7. Under Linux, the app runs fine using Mono + Winforms without any changes &#8211; although there&#8217;s a slight glitch &#8211; the generated URL doesn&#8217;t see to get copied to the clipboard. Let me know your feedback / rants.

(PS: Don&#8217;t judge my code, its horribly n00bish and nowhere close to being called &#8220;professional&#8221;)

[Download Link:][1]  
Sources available on [GitHub][2]

( Based on [Omkar&#8217;s][3] ScreenUp <del datetime="2010-06-02T01:32:56+00:00">and uses <a href="http://www.codeemporium.com/2009/06/14/dot-net-c-sharp-wrapper-for-the-imageshack-xml-api">Bryce&#8217;s C# Wrapper for ImageShack XML API</a></del>. Also, thanks to Omkar for the [selection screenshot library][4]. )

Screenshot of the software in action:  
![IS Uploader][5] 

Update: Bryce&#8217;s imageshack library stopped working, due to a probable change in API by Imageshack. The tool now uploads the image to imgur. Functionality remains the same 🙂

 [1]: http://j.mp/cFESGw
 [2]: http://github.com/SathyaBhat/imageshackuploader
 [3]: http://intelomkar.wordpress.com
 [4]: http://intelomkar.wordpress.com/2009/12/21/screencapture-library/
 [5]: http://img704.imageshack.us/img704/8379/uploadk.jpg
