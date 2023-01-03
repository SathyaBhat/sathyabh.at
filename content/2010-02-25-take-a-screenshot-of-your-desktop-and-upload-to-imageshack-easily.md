---
title: Take a screenshot of your desktop and upload to ImageShack imgur easily
author: Sathyajith Bhat
type: post
date: 2010-02-25T01:28:04+00:00
url: /2010/02/25/take-a-screenshot-of-your-desktop-and-upload-to-imageshack-easily/




categories:
  - Programming
tags:
  - imageshack

---
I wanted a simple tool to upload to Imageshack with minimum fuss and absolutely no config settings, couldn't find any such so I built one myself.  Just extract all the files to a folder, run the executable, and if you want to upload something to  Imageshack, hit PrintScreen and double click the icon on the system tray, it'll automatically upload to <s>ImageShack</s> imgur, and once upload is done, will give you a notification and copy the <s>ImageShack</s> imgur URL to the clipboard.



  
I've been using this for the past few <span style="text-decoration: line-through;">weeks</span> months now, and seems to work fine atleast on Win 7. Under Linux, the app runs fine using Mono + Winforms without any changes - although there's a slight glitch - the generated URL doesn't see to get copied to the clipboard. Let me know your feedback / rants.

(PS: Don't judge my code, its horribly n00bish and nowhere close to being called "professional")

[Download Link:][1]  
Sources available on [GitHub][2]

( Based on [Omkar's][3] ScreenUp <del datetime="2010-06-02T01:32:56+00:00">and uses <a href="https://www.codeemporium.com/2009/06/14/dot-net-c-sharp-wrapper-for-the-imageshack-xml-api">Bryce's C# Wrapper for ImageShack XML API</a></del>. Also, thanks to Omkar for the [selection screenshot library][4]. )

Screenshot of the software in action:  
![IS Uploader][5] 

Update: Bryce's imageshack library stopped working, due to a probable change in API by Imageshack. The tool now uploads the image to imgur. Functionality remains the same 🙂

 [1]: https://j.mp/cFESGw
 [2]: https://github.com/SathyaBhat/imageshackuploader
 [3]: https://intelomkar.wordpress.com
 [4]: https://intelomkar.wordpress.com/2009/12/21/screencapture-library/
 [5]: https://img704.imageshack.us/img704/8379/uploadk.jpg
