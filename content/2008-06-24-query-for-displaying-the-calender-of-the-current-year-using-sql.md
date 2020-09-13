---
title: Query For Displaying The Calender of The Current Year using SQL
author: sathya
type: post
date: 2008-06-24T08:45:56+00:00
url: /2008/06/24/query-for-displaying-the-calender-of-the-current-year-using-sql/

arkayne-time-post:
  - "1325769397"
categories:
  - Computing
tags:
  - calender
  - oracle
  - query
  - SQL

---
Another of things I got via IpMessenger, this query(yes, its a QUERY, not even a full-blown code) returns the calender of the current year. Do note this query will work only in Oracle.

Here's the query.  
<!--more-->

> `SELECT LPAD( MONTH, 20-(20-LENGTH(MONTH))/2 ) MONTH,"Sun", "Mon", "Tue",<br />
"Wed", "Thu", "Fri", "Sat"<br />
FROM (SELECT TO_CHAR(dt,'fmMonthfm YYYY') MONTH,TO_CHAR(dt+1,'iw') week,<br />
MAX (DECODE(TO_CHAR(dt,'d'),'1',LPAD(TO_CHAR(dt,'fmdd'),2))) "Sun",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'2',LPAD(TO_CHAR(dt,'fmdd'),2))) "Mon",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'3',LPAD(TO_CHAR(dt,'fmdd'),2))) "Tue",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'4',LPAD(TO_CHAR(dt,'fmdd'),2))) "Wed",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'5',LPAD(TO_CHAR(dt,'fmdd'),2))) "Thu",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'6',LPAD(TO_CHAR(dt,'fmdd'),2))) "Fri",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'7',LPAD(TO_CHAR(dt,'fmdd'),2))) "Sat"<br />
FROM ( SELECT TRUNC(SYSDATE,'y')-1+ROWNUM dt<br />
FROM all_objects<br />
WHERE ROWNUM <= ADD_MONTHS(TRUNC(SYSDATE,'y'),12) - TRUNC(SYSDATE,'y'))<br />
GROUP BY TO_CHAR(dt,'fmMonthfm YYYY'), TO_CHAR( dt+1, 'iw' ))<br />
ORDER BY TO_DATE( MONTH, 'Month YYYY' ), TO_NUMBER(week);`

A screenshot of part of the result returned  
![Calender][1]  


 [1]: https://img46.imageshack.us/img46/3879/calenderpngeo2.png
