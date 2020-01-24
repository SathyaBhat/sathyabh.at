---
title: PL/SQL Procedure To Reset A Sequence To A Predefined Number in Oracle
author: sathya
type: post
date: 2008-08-11T18:06:27+00:00
url: /2008/08/11/plsql-procedure-to-reset-a-sequence-to-a-predefined-number-in-oracle/

arkayne-time-post:
  - "1325778482"
categories:
  - 'Oracle &amp; PL/SQL Stuff'
  - Programming
tags:
  - oracle
  - PL/SQL
  - Primary key
  - reset
  - sequence
  - SQL

---
Over the period of time that I’ve been working on PL/SQL, the one the thing that we end up doing often is reset the sequences we use for Primary keys in our tables. Why do we do that, you might wonder.

Consider this case:

<!--more-->

You enter some values via the front end. Assume that there are \*a lot\* of fields to be entered. You save them. The <sequence-name>.nextval will pick up the next number in the sequence and goes into your table as the primary key. Now consider that most of the data is common, so instead of entering them via the front-end, you fire up Toad or SQL Developer or PL/SQL Developer and make use of the &#8220;duplicate row” feature. You enter some random value in the PK column, and save it.

Now later on while working on the application, it may happen that the sequence will generate a number which you’d already entered. Now while trying to save this, you’ll end an Oracle error: ORA-00001: Unique Constraint Violated since the sequence number you’re trying to enter is already present, hence violating the constraints.

So here’s a small PL/SQL procedure to reset the sequence to a predefined number. Note that I’m not dropping the sequence or initialising it to zero, that defeats the purpose as I mentioned above

CREATE OR REPLACE PROCEDURE Set\_seq\_To  
(p_Name  IN VARCHAR2,  
p_val   IN NUMBER)  
IS  
v_num  NUMBER;  
BEGIN  
EXECUTE IMMEDIATE &#8216;SELECT &#8216;  
||p_Name  
||&#8217;.NEXTVAL FROM DUAL&#8217; INTO v_num;  
EXECUTE IMMEDIATE &#8216;ALTER SEQUENCE &#8216;  
||p_Name  
||&#8217; INCREMENT BY &#8216;  
||(p\_val &#8211; v\_num &#8211; 1)  
||&#8217; MINVALUE 1&#8242;;  
EXECUTE IMMEDIATE &#8216;SELECT &#8216;  
||p_Name  
||&#8217;.NEXTVAL FROM DUAL&#8217; INTO v_num;  
EXECUTE IMMEDIATE &#8216;ALTER SEQUENCE &#8216;  
||p_Name  
||&#8217; INCREMENT BY 1 &#8216;;  
dbms\_Output.Put\_Line(&#8216;Sequence &#8216;  
||p_Name  
||&#8217; IS NOW AT &#8216;  
||p_val);  
END;

p\_Name is the name of the sequence, and p\_val is the number you want to set it to. I’d say the best number to pass to p_val is to take the Max val of your primary key column. Hope this might help you out.

<div id="scid:0767317B-992E-4b12-91E0-4F059A8CECA8:38d978ff-52f9-4c1b-8bcf-16465f885f88" class="wlWriterSmartContent" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">
  Technorati Tags: <a rel="tag" href="https://technorati.com/tags/Oracle">Oracle</a>,<a rel="tag" href="https://technorati.com/tags/PL%2fSQL">PL/SQL</a>,<a rel="tag" href="https://technorati.com/tags/PLSQL">PLSQL</a>,<a rel="tag" href="https://technorati.com/tags/SQL">SQL</a>,<a rel="tag" href="https://technorati.com/tags/sequence">sequence</a>,<a rel="tag" href="https://technorati.com/tags/Primary+key">Primary key</a>,<a rel="tag" href="https://technorati.com/tags/reset">reset</a>,<a rel="tag" href="https://technorati.com/tags/sathya">sathya</a>,<a rel="tag" href="https://technorati.com/tags/My+World">My World</a>,<a rel="tag" href="https://technorati.com/tags/sathyabh.at">sathyabh.at</a>
</div>
