---
title: PL/SQL Procedure To Reset A Sequence To A Predefined Number in Oracle
author: Sathyajith Bhat
type: post
date: 2008-08-11T18:06:27+00:00
url: /2008/08/11/plsql-procedure-to-reset-a-sequence-to-a-predefined-number-in-oracle/



categories:
  - 'Oracle & PL/SQL Stuff'
tags:  
  - PL/SQL  
  - sequence
  - SQL

---
Over the period of time that I’ve been working on PL/SQL, the one the thing that we end up doing often is reset the sequences we use for Primary keys in our tables. Why do we do that, you might wonder.

Consider this case:



You enter some values via the front end. Assume that there are \*a lot\* of fields to be entered. You save them. The <sequence-name>.nextval will pick up the next number in the sequence and goes into your table as the primary key. Now consider that most of the data is common, so instead of entering them via the front-end, you fire up Toad or SQL Developer or PL/SQL Developer and make use of the "duplicate row” feature. You enter some random value in the PK column, and save it.

Now later on while working on the application, it may happen that the sequence will generate a number which you’d already entered. Now while trying to save this, you’ll end an Oracle error: ORA-00001: Unique Constraint Violated since the sequence number you’re trying to enter is already present, hence violating the constraints.

So here’s a small PL/SQL procedure to reset the sequence to a predefined number. Note that I’m not dropping the sequence or initialising it to zero, that defeats the purpose as I mentioned above

CREATE OR REPLACE PROCEDURE Set\_seq\_To  
(p_Name  IN VARCHAR2,  
p_val   IN NUMBER)  
IS  
v_num  NUMBER;  
BEGIN  
EXECUTE IMMEDIATE 'SELECT '  
||p_Name  
||'.NEXTVAL FROM DUAL' INTO v_num;  
EXECUTE IMMEDIATE 'ALTER SEQUENCE '  
||p_Name  
||' INCREMENT BY '  
||(p\_val - v\_num - 1)  
||' MINVALUE 1&#8242;;  
EXECUTE IMMEDIATE 'SELECT '  
||p_Name  
||'.NEXTVAL FROM DUAL' INTO v_num;  
EXECUTE IMMEDIATE 'ALTER SEQUENCE '  
||p_Name  
||' INCREMENT BY 1 ';  
dbms\_Output.Put\_Line('Sequence '  
||p_Name  
||' IS NOW AT '  
||p_val);  
END;

p\_Name is the name of the sequence, and p\_val is the number you want to set it to. I’d say the best number to pass to p_val is to take the Max val of your primary key column. Hope this might help you out.

