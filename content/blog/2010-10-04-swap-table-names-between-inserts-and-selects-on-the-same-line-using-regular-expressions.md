---
title: Swap Table Names Between Inserts And Selects on the Same Line using Regular Expressions
author: sathya
type: post
date: 2010-10-04T00:14:28+00:00
url: /2010/10/04/swap-table-names-between-inserts-and-selects-on-the-same-line-using-regular-expressions/


arkayne-time-post:
  - "1325728123"
categories:
  - 'Oracle &amp; PL/SQL Stuff'
  - Programming
tags:
  - insert
  - oracle
  - regex
  - regexp
  - regular expressions
  - swap table names

---
Background: For the past few <span style="text-decoration: line-through;">days</span> weeks, I have been working on a way to export selective data from one schema to import into another. Now the problem is that &#8220;selective&#8221; data refers to the data as stored across various tables in the custom application that I&#8217;ve been working on, with elaborate relational links between the tables ( if you&#8217;re curious, the table count on the related data was about 65) &#8211; so it was not just couple of tables that I had to export.  
<!--more-->

So after exploring few alternatives, I concluded that the best way is fetch the related data into the &#8220;export versions&#8221; of these tables, dump these tables using Oracle&#8217;s export tool and re-import them.

Creating the export script wasn&#8217;t that difficult but a rather tedious task. The exports scripts look like

<pre class="brush:sql">DROP TABLE TABLE_NAME1_EXP;
CREATE TABLE_NAME1_EXP AS SELECT * FROM TABLE_NAME1 WHERE_CONDITION;

DROP TABLE TABLE_NAME2_EXP;
CREATE TABLE_NAME2_EXP AS SELECT * FROM TABLE_NAME2 WHERE_CONDITION;

DROP TABLE TABLE_NAME3_EXP;
CREATE TABLE_NAME3_EXP AS SELECT * FROM TABLE_NAME3 WHERE_CONDITION;

DROP TABLE TABLE_NAME4_EXP;
CREATE TABLE_NAME4_EXP AS SELECT * FROM TABLE_NAME4 WHERE_CONDITION;</pre>

&#8230; n times.

Once the export script was ready, added it to batch file which would ask for username, password & service name so as to make it fully automated. Proceeded with testing, then I realized &#8211; to test this end to end, I needed to import the data back in &#8211; and I didn&#8217;t have an import script.

The import script would be the same as the export script, just the source and destination table names swapped, and without the DROP statements either.

So first thing to do was to get rid of the DROP statements. I figured regular expressions would be the best way to get rid of them, and with my rudimentary regexp experience I used Notepad++ ( I <3 Notepad++ ) to remove them &#8211; I used the expression

<pre class="brush:sql">DROP TABLE \w*;</pre>

and replaced it with a space. So that solved my one problem.

Now when it came to part of swapping, I was absolutely clueless as to how to go about doing this. So dropped by [The Roach Motel][1]{#aptureLink_obPD5AwJlF}.

In case you&#8217;re wondering what &#8220;The Roach Motel&#8221; is &#8211; it&#8217;s a room setup within the insanely awesome [Stack Overflow Chat][2]{#aptureLink_rJQCbOcOpE} for the purpose of Code Review and help with bug fixing. Got in touch with Josh, and he was able to whip out a [quick solution][3]{#aptureLink_lmcgQphmfo} using jsfiddle. This saved me atleast 6 hours of tedious work.  I&#8217;m immensely grateful to [Josh][4]{#aptureLink_S6fjAouQRp} for all the help provided by him.

Here&#8217;s the solution:

An HTML Form:

<pre class="brush:html"><textarea id="sathyasql" cols="40" rows="20"></textarea>
<input id="go" type="submit" />
</pre>

JS code for regexp find & replace

<pre class="brush:js">$('go').observe('click',function()
           {
              var sql = $F('sathyasql');
               sql = sql.replace(/INSERT INTO ([^ ]+) AS SELECT \* FROM ([^ ]+)/g,'INSERT INTO $2 AS SELECT * FROM $1');
              $('sathyasql').update(sql).value = sql;
           });
</pre>

For those interested, full [transcript][5]{#aptureLink_8lQS41Ofmn} of my discussions with Josh

 [1]: http://chat.meta.stackoverflow.com/rooms/224/the-roach-motel
 [2]: http://chat.meta.stackoverflow.com/
 [3]: http://jsfiddle.net/M6dxn/1/
 [4]: http://meta.stackoverflow.com/users/131541?tab=accounts#tab-top
 [5]: http://chat.meta.stackoverflow.com/transcript/message/208874#208874
