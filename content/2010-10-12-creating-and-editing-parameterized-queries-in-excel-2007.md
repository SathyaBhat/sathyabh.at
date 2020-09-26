---
title: Creating and Editing Parameterized Queries in Excel 2007
author: sathya
type: post
date: 2010-10-11T22:06:02+00:00
url: /2010/10/12/creating-and-editing-parameterized-queries-in-excel-2007/




categories:
  - Computing
tags:
  - Microsoft Excel
  - SQL

---
I spotted this question on Super User about <a href="https://superuser.com/q/197453/4377" target="_blank">creating parameterized queries in Excel 2007</a> and attempted to answer it - as I thought it would be pretty easy.

And well - it was easy - the part part where you create the query, that is. Now creating _**parameterized**_ queries - now that's something totally different. I searched around a bit for documentation on doing so - and found that any articles on the same were woefully inadequate. To be specific: There are plenty of articles on how to _change_ the parameters - just head over to Properties -> Query Definition -> Parameters. Ok, cool. Now hang on, the Parameters button is disabled. How the heck am I supposed to get it enabled ? I had a ball of a time trying to figure out a way to do it - and in the end, found the answer, and posted it. Figured might as well post it here for my reference&#8230; and for others who are searching for a way to do the same.

<!--more-->

Dunno why MS has made this so complicated, You will have to use Microsoft Query.

Click on Data -> From External Sources -> From Microsoft Query. Choose Data source comes up. Select SQL Server, enter the Authentication details, and select the table

![][1] 

Click on Next, don't select any filtering criteria, choose sort by criteria, click on next. Now, click on View/Edit in MS Query instead of selecting Return to Excel

![][2] 

Click on Finish. Now in MS Query, Click on Criteria -> Add Criteria, choose the operator and let the value be `[]`

![][3] 

Click on File -> return data to Excel. Now Excel should prompt you for the parameter, select the relevant cell

![][4] 

To edit the parameters, click on Data -> Properties -> Finger icon -> Definition -> Parameters

![][5] 

* * *You can also use the SQL query editor and type in the query with the joins and put a 

`?` against the field where the parameter has to be fetched.</p> 

![][6]

 [1]: https://i.imgur.com/xgNTl.jpg
 [2]: https://i.imgur.com/UfJ1F.png
 [3]: https://i.imgur.com/TnJoi.png
 [4]: https://i.imgur.com/a2l5C.png
 [5]: https://i.imgur.com/XXhfs.png
 [6]: https://i.imgur.com/NgXxc.png
