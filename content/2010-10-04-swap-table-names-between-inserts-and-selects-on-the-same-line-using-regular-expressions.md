---
title: Swap Table Names Between Inserts And Selects on the Same Line using Regular Expressions
author: Sathyajith Bhat
type: post
date: 2010-10-04T00:14:28+00:00
url: /2010/10/04/swap-table-names-between-inserts-and-selects-on-the-same-line-using-regular-expressions/




categories:
  - 'Oracle & PL/SQL Stuff'
  - Programming
tags:
  - insert
  - oracle
  - regex
  - regexp
  - regular expressions
  - swap table names

---
Background: For the past few <span style="text-decoration: line-through;">days</span> weeks, I have been working on a way to export selective data from one schema to import into another. Now the problem is that "selective" data refers to the data as stored across various tables in the custom application that I've been working on, with elaborate relational links between the tables ( if you're curious, the table count on the related data was about 65) - so it was not just couple of tables that I had to export.  


So after exploring few alternatives, I concluded that the best way is fetch the related data into the "export versions" of these tables, dump these tables using Oracle's export tool and re-import them.

Creating the export script wasn't that difficult but a rather tedious task. The exports scripts look like

<pre class="brush:sql">DROP TABLE TABLE_NAME1_EXP;
CREATE TABLE_NAME1_EXP AS SELECT * FROM TABLE_NAME1 WHERE_CONDITION;

DROP TABLE TABLE_NAME2_EXP;
CREATE TABLE_NAME2_EXP AS SELECT * FROM TABLE_NAME2 WHERE_CONDITION;

DROP TABLE TABLE_NAME3_EXP;
CREATE TABLE_NAME3_EXP AS SELECT * FROM TABLE_NAME3 WHERE_CONDITION;

DROP TABLE TABLE_NAME4_EXP;
CREATE TABLE_NAME4_EXP AS SELECT * FROM TABLE_NAME4 WHERE_CONDITION;</pre>

&#8230; n times.

Once the export script was ready, added it to batch file which would ask for username, password & service name so as to make it fully automated. Proceeded with testing, then I realized - to test this end to end, I needed to import the data back in - and I didn't have an import script.

The import script would be the same as the export script, just the source and destination table names swapped, and without the DROP statements either.

So first thing to do was to get rid of the DROP statements. I figured regular expressions would be the best way to get rid of them, and with my rudimentary regexp experience I used Notepad++ ( I <3 Notepad++ ) to remove them - I used the expression

<pre class="brush:sql">DROP TABLE \w*;</pre>

and replaced it with a space. So that solved my one problem.

Now when it came to part of swapping, I was absolutely clueless as to how to go about doing this. So dropped by [The Roach Motel][1].

In case you're wondering what "The Roach Motel" is - it's a room setup within the insanely awesome [Stack Overflow Chat][2] for the purpose of Code Review and help with bug fixing. Got in touch with Josh, and he was able to whip out a [quick solution][3] using jsfiddle. This saved me atleast 6 hours of tedious work.  I'm immensely grateful to [Josh][4] for all the help provided by him.

Here's the solution:

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

For those interested, full [transcript][5] of my discussions with Josh

 [1]: https://chat.meta.stackoverflow.com/rooms/224/the-roach-motel
 [2]: https://chat.meta.stackoverflow.com/
 [3]: https://jsfiddle.net/M6dxn/1/
 [4]: https://meta.stackoverflow.com/users/131541?tab=accounts#tab-top
 [5]: https://chat.meta.stackoverflow.com/transcript/message/208874#208874
