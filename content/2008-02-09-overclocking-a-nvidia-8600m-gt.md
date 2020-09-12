---
title: Overclocking a NVIDIA 8600m GT
author: sathya
type: post
date: 2008-02-08T21:39:01+00:00
url: /2008/02/09/overclocking-a-nvidia-8600m-gt/

arkayne-time-post:
  - "1325774161"
categories:
  - Tutorials
tags:
  - ATiTool
  - NVIDIA
  - OC
  - overclock

---
### Requirements

  * Latest nVidia drivers
  * ATiTool 0.26/RivaTuner 2.06
  * A bit of patience

1. Getting the latest drivers.  
Unfortunately, the drivers from nvidia's site won't work for a laptop, as they don't recognize the mobile versions. What you need are drivers from https://www.laptopvideo2go.com Also do note that NOT ALL drivers support OC'ing. The latest that I tried were 171.16.

Grab the latest drivers from [here][1]. Also, pick up the modified inf files from the same thread. Now extract the downloaded drivers to a folder(the .exe is a self extracting 7z compressed file). Next, goto the folder where the drivers are extracted. Replace the inf file with the modded inf file you have downloaded. DO NOT run the setup.exe file. You will have to update the drivers manually, using the Have Disk Method.  
To do this, goto Control Panel, Double click the System, Click on Hardware Tab and Choose the Device Manager. Expand Display adapters, right click on the 8600m GT and Click on Properties. Click on Driver tab, and Choose update drivers.  
<!--more-->

  
![Update][2] 

Select no when prompted to Check for drivers using Windows Update .

Next, click on Install from a list or specific location.  
![Update from specific location][3]  
Click on Next. In the next dialog, click on Don't search radio button and Click next.  
![Manual Install][4]  
In the next dialog, click on Have Disk button, and point to the location where you extracted the inf files,  
click on open and click on Next.  
![Have Disk][5]  
When prompted to restart the system, do so.  
After this, you're ready to start overclocking!  
Install ATiTool and run it.  
![ATi Tool][6]  
The last 2 sliders(Core and memory for 3D performance sliders) are what's required. Start increasing the Core speed slider, by 5MHz at time, and click on Set Clock button. Once this is done, click on scan artifacts. If the cube is rendered perfectly, then repeat the process.  
![No Artifacts][7]  
At a certain clock, you will start to see artifacts(as seen in the picture).  
![Artifacting][8]  
Even at the slightest hints of artifacts, reduce the speed by about 10MHz, and Click on Scan for artifacts. Once you've reached a sweetspot, Click on scan artifacts again, and let it run for a longer time. Or just play your favorite game, for an hour or so. Any signs of instability, or artifacts, or extremely high temperatures, higher than about 66-68 deg , reduce the speeds immediately! Run repeat the same steps for the memory clocks too. Once you've finalized on the speeds, Click on New, give a suitable name and save the profile. Next time you want to play a game, just load AtiTool, and load the desired profile! Hope this helps!

Performance Results:

Stock speed: 475(core)/400(mem)  
3dMark 06 Results  
Using 163.16 drivers (stock speeds): **3382 3D Marks** 

OC was not possible with this one

171.16 drivers(stock speeds) : **3587 3D Marks** -> ~200 points increase with just a driver upgrade!

OC'd speeds: 630/505(any higher than 640 would give artifacts, so to give a comfortable margin, set it to 630): **4396 3D Marks** 😀 \:D/

Nearly a 1000point increase. I think increasing the mem clock I can crack the 4500 mark, but with the current clocks, the peak temp is 66, so I'm happy \:D/

 [1]: https://www.laptopvideo2go.com/forum/index.php?showforum=73
 [2]: https://img225.imageshack.us/img225/2740/updatexm8.jpg
 [3]: https://img136.imageshack.us/img136/1663/update1bb8.jpg
 [4]: https://img218.imageshack.us/img218/8094/update2nf2.jpg
 [5]: https://img221.imageshack.us/img221/601/update3bz2.jpg
 [6]: https://img221.imageshack.us/img221/8127/atitoolmo3.jpg
 [7]: https://img240.imageshack.us/img240/518/noartifactsrz8.jpg
 [8]: https://img233.imageshack.us/img233/8664/artifactslo6.jpg
