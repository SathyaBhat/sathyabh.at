---
title: The Power and Simplicity of Oracle Hierarchical Queries
author: Sathyajith Bhat
type: post
date: 2009-01-19T04:12:55+00:00
url: /2009/01/19/the-power-and-simplicity-of-oracle-hierarchical-queries/


categories:
  - 'Oracle & PL/SQL Stuff'
tags:
  - hierarchical queries
  - oracle
  - PL/SQL
  - query
  - SQL

---
They say "Necessity is the Power of Invention" - a quote which I fully understood the impact today. I've been trying to understand Oracle's Hierarchical Queries for a while now, but never fully understood the situation under which or when it would be used. Yesterday I got a reason to use it. Let me begin.

<p style="text-align: left;">
  <!--more-->
  
  <a href="https://i.sathyabh.at/sb/2009/01/menu.png"><img class="size-medium wp-image-209 aligncenter" title="menu" src="https://i.sathyabh.at/sb/2009/01/menu-300x178.png" alt="menu" width="300" height="178" /></a>The above picure shows the menu structure of the our application. Now the implementer wanted the menu structure, of each and _every_ module, in a spreadsheet so that he could forward it to the client and get the user authorization thing going(ie, who's got authority to view/edit etc). Now under each module we have several menus and submenus, and manually entering these would be like ultimate FAIL (later ananlysis showed on an average, each module had about 80 entries). So I was figuring out how to extract this. Now I knew that all these entries were there in the database I was struggling with the query to extract it.
</p>

So the first query I came up was this:

`<span style="font-family: Courier New; font-size: 10pt;"><br />
<span style="color: blue; ">SELECT</span> <span style="color: maroon; ">MENU_SCR_NAME</span><br />
<span style="color: blue; ">FROM</span> <span style="color: maroon; ">MENU_MENUS</span><br />
<span style="color: blue; ">WHERE</span> <span style="color: maroon; ">MENU_PARENT_ID</span> <span style="color: silver; ">=</span> <span style="color: red; ">'101'</span></span>`

This is what the query results were - a simple output.

<span style="font-family: Courier New; font-size: 10pt;"><a href="https://i.sathyabh.at/sb/2009/01/query1.png"><img class="alignnone size-full wp-image-211" title="Query results" src="https://i.sathyabh.at/sb/2009/01/query1.png" alt="Query results" width="180" height="338" /></a></span>

Now I knew I'd be going nowhere with this simple query, and I knew normal joins won't work, so I started looking at Hierarchical queries. Hierarchical queries(going to refer as h-queries) basically allow you to build queries, based on well, hierarchies. Parent - Child Relationships. Tree-Leaf style. Read a bit on h-queries and reconstructed the SQL query to the one below.

`<span style="font-family: Courier New; font-size: 10pt;"><span style="color: blue;">SELECT</span> <span style="color: maroon;">MENU_SCR_NAME</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">MENU_MENUS</span><br />
<span style="color: blue;">CONNECT</span> <span style="color: blue;">BY</span> <span style="color: blue;">PRIOR</span> <span style="color: maroon;">MENU_ID</span> <span style="color: silver;">=</span> <span style="color: maroon;">MENU_PARENT_ID</span><br />
<span style="color: blue;">START</span> <span style="color: blue;">WITH</span> <span style="color: maroon;">MENU_ID</span> <span style="color: silver;">=</span> <span style="color: red;">'101'</span><span style="color: silver;">;</span><br />
</span>`  
The result of the query is shown below:

<span style="font-family: Courier New; font-size: 10;"><a href="https://i.sathyabh.at/sb/2009/01/query2.png"><img class="alignnone size-full wp-image-212" title="query2" src="https://i.sathyabh.at/sb/2009/01/query2.png" alt="query2" width="215" height="350" /></a></span>

While the result of the query looks the same as the first, I knew that it was returning the results in a hierarchy,just check the first image. The keyword for this query is "Connect by" and "Prior" which transforms the query into a h-query. The "connect by" and "prior" gives the conditions for hierarachy in the query, with the column next to "prior" being the child column and the one next to equality being the parent column. The "start with" keyword tells Oracle which is the root record.

Now make things a little complicated, the database contains more records than what's necessary, and I had to filter them based on user authorization conditions as well. So I added a subquery to filter out those records which belong to the superuser.

So the query now became a little bit more (unnecessarily) complicated:  
`<br />
<span style="font-family: Courier New; font-size: 10pt;"><span style="color: blue;">SELECT</span> <span style="color: #ff0080;"><strong>Lpad</strong></span><span style="color: maroon;">(</span><span style="color: maroon;">menu_scr_name</span><span style="color: silver;">,</span><span style="color: #ff0080;"><strong>Length</strong></span><span style="color: maroon;">(</span><span style="color: maroon;">menu_scr_name</span><span style="color: maroon;">)</span> <span style="color: silver;">+</span> <span style="color: blue;">LEVEL</span> <span style="color: silver;">*</span> <span style="color: black;">4</span> <span style="color: silver;">-</span> <span style="color: black;">4</span><span style="color: silver;">,</span><span style="color: red;">'-'</span><span style="color: maroon;">)</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_menus</span><br />
<span style="color: blue;">WHERE</span> <span style="color: maroon;">menu_id</span> <span style="color: blue;">IN</span> <span style="color: maroon;">(</span><span style="color: blue;">SELECT</span> <span style="color: maroon;">um_menu_id</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_user_menus</span><br />
<span style="color: blue;">WHERE</span> <span style="color: maroon;">um_group_id</span> <span style="color: silver;">=</span> <span style="color: red;">'USGRP'</span><br />
<span style="color: blue;">AND</span> <span style="color: maroon;">um_menu_id</span> <span style="color: blue;">IN</span> <span style="color: maroon;">(</span><span style="color: blue;">SELECT</span> <span style="color: maroon;">menu_id</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_menus</span><br />
<span style="color: blue;">CONNECT</span> <span style="color: blue;">BY</span> <span style="color: blue;">PRIOR</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: maroon;">menu_parent_id</span><br />
<span style="color: blue;">START</span> <span style="color: blue;">WITH</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: red;">'101'</span><span style="color: maroon;">)</span><span style="color: maroon;">)</span><br />
<span style="color: blue;">CONNECT</span> <span style="color: blue;">BY</span> <span style="color: blue;">PRIOR</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: maroon;">menu_parent_id</span><br />
<span style="color: blue;">ORDER</span> <span style="color: blue;">BY</span> <span style="color: maroon;">menu_id</span><br />
</span>`  
The Lpad function is an Oracle PL/SQL function which adds padding of a specified character to the left. The results were not exactly what I was looking for.

[<img class="alignnone size-full wp-image-216" title="query3" src="https://i.sathyabh.at/sb/2009/01/query3.png" alt="query3" width="160" height="360" />][1]

A bit of further reading and I came to know that order by destroys the hierarchy, and "order siblings" by is what is supported to be used.

So Modified the query to:  
`<span style="font-family: Courier New; font-size: 10pt;"><span style="color: blue;">SELECT</span> <span style="color: #ff0080;"><strong>Lpad</strong></span><span style="color: maroon;">(</span><span style="color: maroon;">menu_scr_name</span><span style="color: silver;">,</span><span style="color: #ff0080;"><strong>Length</strong></span><span style="color: maroon;">(</span><span style="color: maroon;">menu_scr_name</span><span style="color: maroon;">)</span> <span style="color: silver;">+</span> <span style="color: blue;">LEVEL</span> <span style="color: silver;">*</span> <span style="color: black;">4</span> <span style="color: silver;">-</span> <span style="color: black;">4</span><span style="color: silver;">,</span><span style="color: red;">'-'</span><span style="color: maroon;">)</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_menus</span><br />
<span style="color: blue;">WHERE</span> <span style="color: maroon;">menu_id</span> <span style="color: blue;">IN</span> <span style="color: maroon;">(</span><span style="color: blue;">SELECT</span> <span style="color: maroon;">um_menu_id</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_user_menus</span><br />
<span style="color: blue;">WHERE</span> <span style="color: maroon;">um_group_id</span> <span style="color: silver;">=</span> <span style="color: red;">'USGRP'</span><br />
<span style="color: blue;">AND</span> <span style="color: maroon;">um_menu_id</span> <span style="color: blue;">IN</span> <span style="color: maroon;">(</span><span style="color: blue;">SELECT</span> <span style="color: maroon;">menu_id</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_menus</span><br />
<span style="color: blue;">CONNECT</span> <span style="color: blue;">BY</span> <span style="color: blue;">PRIOR</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: maroon;">menu_parent_id</span><br />
<span style="color: blue;">START</span> <span style="color: blue;">WITH</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: red;">'101'</span><span style="color: maroon;">)</span><span style="color: maroon;">)</span><br />
<span style="color: blue;">CONNECT</span> <span style="color: blue;">BY</span> <span style="color: blue;">PRIOR</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: maroon;">menu_parent_id</span><br />
<span style="color: blue;">ORDER</span> <span style="color: blue;">SIBLINGS</span> <span style="color: blue;">BY</span> <span style="color: maroon;">menu_id</span><br />
</span>`

And it all came into place. Almost.

Have a look:

[<img class="alignnone size-full wp-image-217" title="query4" src="https://i.sathyabh.at/sb/2009/01/query4.png" alt="query4" width="189" height="480" />][2]

Unfortunately, it wasn't quite right, as the query was going into an almost infinite loop, as the child record itself became the root record.

I had a look at the query again, and realized that my query itself was wrong, as corrected it to  
`<br />
<span style="font-family: Courier New; font-size: 10pt;"><span style="color: blue;">SELECT</span> <span style="color: #ff0080;"><strong>Lpad</strong></span><span style="color: maroon;">(</span><span style="color: maroon;">menu_scr_name</span><span style="color: silver;">,</span><span style="color: #ff0080;"><strong>Length</strong></span><span style="color: maroon;">(</span><span style="color: maroon;">menu_scr_name</span><span style="color: maroon;">)</span> <span style="color: silver;">+</span> <span style="color: blue;">LEVEL</span> <span style="color: silver;">*</span> <span style="color: black;">4</span> <span style="color: silver;">-</span> <span style="color: black;">4</span><span style="color: silver;">,</span><span style="color: red;">'-'</span><span style="color: maroon;">)</span> <span style="color: maroon;">"Menu"</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_menus</span><br />
<span style="color: blue;">WHERE</span> <span style="color: maroon;">menu_id</span> <span style="color: blue;">IN</span> <span style="color: maroon;">(</span><span style="color: blue;">SELECT</span> <span style="color: maroon;">um_menu_id</span><br />
<span style="color: blue;">FROM</span> <span style="color: maroon;">menu_user_menus</span><br />
<span style="color: blue;">WHERE</span> <span style="color: maroon;">um_group_id</span> <span style="color: silver;">=</span> <span style="color: red;">'USGRP'</span><span style="color: maroon;">)</span><br />
<span style="color: blue;">CONNECT</span> <span style="color: blue;">BY</span> <span style="color: blue;">NOCYCLE</span> <span style="color: blue;">PRIOR</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: maroon;">menu_parent_id</span><br />
<span style="color: blue;">START</span> <span style="color: blue;">WITH</span> <span style="color: maroon;">menu_id</span> <span style="color: silver;">=</span> <span style="color: red;">'101'</span><br />
<span style="color: blue;">ORDER</span> <span style="color: blue;">SIBLINGS</span> <span style="color: blue;">BY</span> <span style="color: maroon;">menu_seq_no</span><span style="color: silver;">;</span><br />
</span>`

So in essence, I got rid of the unnecessary inner sub-query and voila!

[<img class="alignnone size-full wp-image-218" title="query5" src="https://i.sathyabh.at/sb/2009/01/query5.png" alt="query5" width="215" height="520" />][3]

 [1]: https://i.sathyabh.at/sb/2009/01/query3.png
 [2]: https://i.sathyabh.at/sb/2009/01/query4.png
 [3]: https://i.sathyabh.at/sb/2009/01/query5.png
