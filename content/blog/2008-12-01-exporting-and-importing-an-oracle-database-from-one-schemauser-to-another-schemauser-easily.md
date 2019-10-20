---
title: Exporting and Importing An Oracle database from one schema/user to Another schema/user easily
author: sathya
type: post
date: 2008-12-01T03:40:25+00:00
url: /2008/12/01/exporting-and-importing-an-oracle-database-from-one-schemauser-to-another-schemauser-easily/

arkayne-time-post:
  - "1325790515"
categories:
  - 'Oracle &amp; PL/SQL Stuff'
  - Programming
tags:
  - data files
  - exp
  - export
  - imp
  - import
  - oracle
  - tablespace

---
Couple of days ago at work I was asked to create a new environment(schema, user) for specific application testing conditions. While that was no big deal, I was also asked to import all the data from existing production environment into a new environment &#8211; and I was in a bit of bother here &#8211; generally the whole importing/exporting is done by DBA&#8217;s not developers. While I knew the usage of exp and imp commands, creating schema would require stuff like tablespace creating, adding data files and more importantly &#8211; grants which I had NO clue on. So after a bit of experimenting and consulting with my fellow colleague Rupam, I finally managed to export and import the data. This post is on how-to go about doing it.

If you want to skip all the commands and all just get the import / export done in 1-click try <a href="http://www.softpedia.com/get/Internet/Servers/Database-Utils/Easy-Dump-Oracle.shtml" target="_blank">Easy Dump Oracle 1.1</a> &#8211; a tool which I found on the database server after all the headbanging 😐

Anyways here&#8217;s a step by step  process on how you export and import the data &#8211; do note that Easy Dump Oracle can import data ONLY if required grants are given to the user and tablespace has been allocated. For that you need to follow the below mentioned steps.

<!--more-->

First, export the user/schema that you want to import to. For that open the command prompt and type

> `exp user/password@hoststring file=filename.dmp log=filename.log`

Next, we&#8217;ll have to create a tablespace and associate that tablespace to a datafile. For that we&#8217;ll need to know the location where the datafiles are stored. If you don&#8217;t know the location of datafiles then find out using the query

> `select file_name from dba_data_files;`

Make a note of the location of the data files the above query shows.  
Next create a tablespace and associate a datafile. For that, open SQL*Plus prompt and type

> `create tablespace <tablespace-name>   datafile '<location-of-datafile-datafile-name>' size <desired-size>;`

The can be as per your needs. If you aren&#8217;t sure if the size specified here is sufficient add &#8216;autoextend on &#8216; to the above query, else you might end up with a import terminated halfway because of insuffient space allocated.

Next create a user

> `Create user <username>  identified by <password><br />
default tablespace <name-of-tablespace> quota unlimited on <name-of-tablespace> ;`

Next, give the required grants

> `grant connect,create session,imp_full_database to <username>;`

Now finally import the data you&#8217;d exported earlier by typing the the below at the command prompt

> `imp username/password@hoststring file=filename.dmp log=filename.log full=y`
