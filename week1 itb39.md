

SQL\*Plus: Release 19.0.0.0.0 - Production on Fri Jan 9 08:40:53 2026

Version 19.3.0.0.0



Copyright (c) 1982, 2019, Oracle.  All rights reserved.



Enter user-name: itb39@orcl

Enter password:



Connected to:

Oracle Database 19c Enterprise Edition Release 19.0.0.0.0 - Production

Version 19.3.0.0.0

**1. Create a table employee with ( emp\_no, emp\_name, emp\_address)**

SQL> create table employee(emp\_no number(10) primary key, emp\_name varchar(20), emp\_address varchar(30));



Table created.

**2. Insert five employees information.**

SQL> insert into employee values (1,'josh','blah');



1 row created.



SQL> insert into employee values (2, 'hridini', 'ahm');



1 row created.



SQL> insert into employee values (4, 'xyz', 'udupi');



1 row created.



SQL> insert into employee values (21, 'kavish', 'footpath');



1 row created.



SQL> select emp\_name from employee

&nbsp; 2

**3. Display names of all employees.**



SQL> select emp\_name from employee;



EMP\_NAME

--------------------

josh

hridini

xyz

kavish



SQL> insert into employee values(3, 'jess', 'abc');



1 row created.



SQL> select emp\_name from employee;



EMP\_NAME

--------------------

josh

hridini

xyz

kavish

jess



SQL> update employee set emp\_address='MANIPAL' where emp\_address='ahm';



1 row updated.

**4. Display all emp from 'MANIPAL'**

SQL> select \* from employee where emp\_address='MANIPAL';



&nbsp;   EMP\_NO EMP\_NAME             EMP\_ADDRESS

---------- -------------------- ------------------------------

&nbsp;        2 hridini              MANIPAL



**5. Add a column named salary to employee table.**

SQL> alter table employee add(salary number(8));



Table altered.



SQL> insert into employee(salary) values (10000),(10000),(15000),(0),(6000);

insert into employee(salary) values (10000),(10000),(15000),(0),(6000)

&nbsp;                                          \*

ERROR at line 1:

ORA-00933: SQL command not properly ended





SQL> insert into employee(salary) values (10000),(10000),(15000),(0),(6000);

insert into employee(salary) values (10000),(10000),(15000),(0),(6000)

&nbsp;                                          \*

ERROR at line 1:

ORA-00933: SQL command not properly ended





SQL> insert into employee(salary) values (10000);

insert into employee(salary) values (10000)

\*

ERROR at line 1:

ORA-01400: cannot insert NULL into ("ITB39"."EMPLOYEE"."EMP\_NO")





SQL> select \* from employee

&nbsp; 2

SQL> select \* from employee;



&nbsp;   EMP\_NO EMP\_NAME             EMP\_ADDRESS                        SALARY

---------- -------------------- ------------------------------ ----------

&nbsp;        1 josh                 blah

&nbsp;        2 hridini              MANIPAL

&nbsp;        4 xyz                  udupi

&nbsp;       21 kavish               footpath

&nbsp;        3 jess                 abc



**6. Assign the salary for all employees.**

SQL> update employee set salary=10000 where emp\_no=1;



1 row updated.



SQL> update employee set salary=10000 where emp\_no=2;



1 row updated.



SQL> update employee set salary=15000 where emp\_no=3;



1 row updated.



SQL> update employee set salary=1 where emp\_no=21;



1 row updated.



SQL> update employee set salary=0 where emp\_no=21;



1 row updated.



SQL> update employee set salary=7000 where emp\_no=3;



1 row updated.



SQL> desc table employee

Usage: DESCRIBE \[schema.]object\[@db\_link]

**7. View the structure of the table employee using describe.**



SQL> desc employee

&nbsp;Name                                      Null?    Type

&nbsp;----------------------------------------- -------- ----------------------------

&nbsp;EMP\_NO                                    NOT NULL NUMBER(10)

&nbsp;EMP\_NAME                                           VARCHAR2(20)

&nbsp;EMP\_ADDRESS                                        VARCHAR2(30)

&nbsp;SALARY                                             NUMBER(8)



SQL> insert into employee values(6, 'joe', 'MANGALORE', 10000);



1 row created.



SQL> select \* from employee;



&nbsp;   EMP\_NO EMP\_NAME             EMP\_ADDRESS                        SALARY

---------- -------------------- ------------------------------ ----------

&nbsp;        1 josh                 blah                                10000

&nbsp;        2 hridini              MANIPAL                             10000

&nbsp;        4 xyz                  udupi

&nbsp;       21 kavish               footpath                                0

&nbsp;        3 jess                 abc                                  7000

&nbsp;        6 joe                  MANGALORE                           10000



6 rows selected.

**8. delete all emp from mangalore**

SQL> delete from employee where emp\_address='MANGALORE';



1 row deleted.



SQL> select \* from employee;



&nbsp;   EMP\_NO EMP\_NAME             EMP\_ADDRESS                        SALARY

---------- -------------------- ------------------------------ ----------

&nbsp;        1 josh                 blah                                10000

&nbsp;        2 hridini              MANIPAL                             10000

&nbsp;        4 xyz                  udupi

&nbsp;       21 kavish               footpath                                0

&nbsp;        3 jess                 abc                                  7000



SQL> rename employee to employee1

&nbsp; 2

**9. Rename employee as employee1.**

SQL> rename employee to employee1;



Table renamed.



**10. Drop the table employee1.**

SQL>drop table employee1;







