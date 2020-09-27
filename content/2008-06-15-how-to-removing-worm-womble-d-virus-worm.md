---
title: '[How To] Removing Worm/Womble.D – Virus/Worm'
author: sathya
type: post
date: 2008-06-15T09:55:04+00:00
url: /2008/06/15/how-to-removing-worm-womble-d-virus-worm/



categories:
  - Computing
tags:
  - antivirus

---

Well as mentioned <a href="https://sathyabh.at/2008/06/15/my-laptop-gets-an-attack/" target="_blank">here</a> my system was infected by this worm, so I thought I’d do a short post on how to fix this, as most Anti Virus Programs don’t get rid of this cleanly.

First thing, if you’re on the internet, GO OFFLINE! Disconnect, switch off the modem/router, pull the LAN/USB cable, just go offline. This is critical. Why you may ask?

<!--more-->



First, **Womble** is described as 

> Win32/Womble.D is a mass-mailing worm that may be distributed both as an executable or as a malformed Windows Media file exploiting the MS06-001 vulnerability. It may also replicate via network shares. It can be used to periodically download and execute arbitrary files on an affected machine.

And that’s the reason why you have to go offline, since even though the anti-virus might be disinfecting your system, there’s every chance that the worm might keep on downloading and infecting, leading to a never ending process.

Luckily the worm isn’t destructive. Here’s a description of what the worm does:

> It creates the following directories:  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\dvd_info  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\free  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\h_core  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\l_this  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\lunch  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\my_staff  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\new_mp3  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\new_video  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\photo  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\sh_docs  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\take_it  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\video  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\xxx 
> 
> It drops copies of itself using a filename from lists, the following names, to all of the above directories  
> &#160;&#160; • bush  
> &#160;&#160; • Me  
> &#160;&#160; • My passwords  
> &#160;&#160; • MyWife  
> &#160;&#160; • Seduction secrets  
> &#160;&#160; • MySexMovie  
> &#160;&#160; • MySexPicture  
> &#160;&#160; • WallPaper  
> &#160;&#160; • anna  
> &#160;&#160; • Windows serial number  
> &#160;&#160; • GoogleHack  
> &#160;&#160; • OurNewCar  
> &#160;&#160; • OurNewHouse 
> 
> &#160;&#160; • .doc  
> &#160;&#160; • .jpg  
> &#160;&#160; • .txt 
> 
> &#160;&#160; • .exe  
> &#160;&#160; • .pif
> 
> It tries to download some files: 
> 
> – The location is the following:  
> &#160;&#160; • support.365soft.info/current/\***\***\****  
> This file may contain further download locations and might serve as source for new threats. 
> 
> – The location is the following:  
> &#160;&#160; • support.365soft.info/current/\***\***\****  
> This file may contain further download locations and might serve as source for new threats. 
> 
> – The location is the following:  
> &#160;&#160; • support.365soft.info/current/\***\***\****  
> This file may contain further download locations and might serve as source for new threats.

Now I hope you have a decent anti-virus software installed. If not, get one! Recommendations include Kaspersky, NOD32 for paid and AVG Free 8 for free anti-virus. Install these, during scanning when prompted with the action, click on Delete.

If you don’t have an AV/can’t install one, then you’ll have to manually remove it for this, open the registry editor, by Clicking on Start, Run and typing regedit and pressing enter.

Navigate to HKEY\_LOCAL\_MACHINE (abbreviated to HKLM) and then delete the following entry

> – [HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run]  
> &#160;&#160; • windows_startup=%SYSDIR%\%random words%.exe

Next, delete the following entries

> – [HKLM\SOFTWARE\WinUpdate]  
> &#160;&#160; • "Version"=dword:00000004 
> 
> – [HKLM\SOFTWARE\WinUpload]  
> &#160;&#160; • "bot1.exe"=dword:00000002  
> &#160;&#160; • "bot2.exe"=dword:00000002  
> &#160;&#160; • "l.exe"=dword:00000002  
> &#160;&#160; • "t169.exe"=dword:00000002 
> 
> – [HKCU\Software\Microsoft\WAB\WAB4]  
> &#160;&#160; • "FirstRun"=dword:00000001 
> 
> – [HKCU\Software\Microsoft\Windows\CurrentVersion]  
> &#160;&#160; • "wmf.1.1"=dword:01c6db12  
> &#160;&#160; • "wmf.1.2"=dword:e8fc9740

where HKCU is an abbreviation for HKEY\_CURRENT\_USER

Then head over to [HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon]  
You will see something like 

> [HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon] 
> 
>   * "Shell"="Explorer.exe%empty spaces% %SYSDIR%\%random words%.exe"
>   * &#160; "Userinit"="%SYSDIR%\userinit.exe%empty spaces% ,%SYSDIR%\%random words%.exe"

Change these to 

> [HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon] 
> 
>   * "Shell"="Explorer.exe"
>   * "Userinit"="%SYSDIR%\userinit.exe”</p> 

Now reboot your machine. Next, if you’ve Disabled Show Hidden Files, you should enable it by going to My Computer, Tools –> Folder Options, Click on View –> Show Hidden Files.

Next, goto %home%\Local Settings\Application Data\Microsoft\&#160; where %home% is the current user folder, ie, if Windows is installed in C, and the user is user1 then %home% refers to 

C:\Documents And Settings\user1\

Delete the WinTools folder. After this your system should be free from the worm

