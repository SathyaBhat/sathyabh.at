---
title: 'Fix Initialization Error: LoadLibrary oci.dll returned 0 while trying to connect to Oracle using PL/SQL Developer'
author: sathya
type: post
date: 2011-03-21T08:38:24+00:00
url: /2011/03/21/fix-initialization-error-loadlibrary-oci-dll-returned-0-while-trying-to-connect-to-oracle-using-plsql-developer/


arkayne-time-post:
  - "1325789975"
categories:
  - 'Oracle & PL/SQL Stuff'
tags:
  - database
  - instant client
  - oracle
  - PL/SQL
  - PL/SQL Developer

---
Quick post: I was trying to connect to a 64-bit Oracle database using PL/SQL Developer. Despite ORACLE_HOME being set the right values and oci.dll available, PL/SQL Developer could not connect to the database.

<!--more-->

Further probing indicated that the Oracle installation was a 64-bit one, and PL/SQL Developer is incapable of loading 64-bit version of oci.dll file. To fix this, download the 32-bit version of [Oracle Instant Client][1], extract it to a directory such as \instant_client.

Next, configure PL/SQL Developer to use this version by clicking on Tool menus -> Preferences. Under Oracle Home, point to the location where you had extracted Instant client (\instant\_client, in this case)  and under location of OCI Library, point to the oci.dll file present in location where you had extracted Instant client ( \instant\_client\oci.dll). Restart PL/SQL Developer and you should be able to connect now.

 [1]: https://www.oracle.com/technetwork/database/features/instant-client/index-097480.html
