---
title: Batch file to delete files older than x days
author: Sathyajith Bhat
type: post
date: 2010-11-10T18:27:21+00:00
url: /2010/11/10/batch-file-to-delete-files-older-than-x-days/




categories:
  - Computing
tags:
  - backup
  - batch-file
  - command-line

---
At work, I have bunch of batch files which take an export from Oracle database, compress them and move them to their respective folders. In addition to this, the scripts also copy the Oracle forms executibles ("fmx"), reports ("rdf") and other miscellaneous files to the backup locations and these are further compressed. The compressed files are then transferred over to the [SAN][1].

<!--more-->

Now the problem was that these backup files would still remain on the hard drive, littering the folders and resulting in waste of space - I was looking for an alternative to get rid of these files via a scripted approach. The catch is that this is a Windows server and I'm restricted to the CLI that Windows provides - and no PowerShell either. So while researching for ways to select files older than x days, I came across forfiles command on [Stack Overflow][2] (God bless thee).

<pre class="brush:bash">forfiles: Select a file (or set of files) and execute a command on each file.</pre>

Perfect. Exactly what I needed. After reading the help file and experimenting with it, I rolled out a script which will delete any file older than 30 days.

<pre class="brush:bash">@echo off
@Echo Deleting files older than 30 days...

forfiles /p g:\backup /d -30 /c "cmd /c del @file"</pre>

So this will basically search for any file(s) older than 30 days ( based on the Last Modification Date attribute) in the path g:\backup and will execute del @file where del == delete, @file is the variable which holds the filename.

You can further filter out the files by using /m switch. I'd recommend you have a look at the description [over here][3].

 [1]: https://en.wikipedia.org/wiki/Storage%20area%20network
 [2]: https://stackoverflow.com/q/51054/92837
 [3]: https://ss64.com/nt/forfiles.html
