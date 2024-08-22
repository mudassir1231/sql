# sql

mysql> use mudassir
Database changed
mysql> create table md(id int(10),name varchar(10) );
Query OK, 0 rows affected, 1 warning (0.04 sec)

mysql> clear
mysql> ;
ERROR: 
No query specified

mysql> select * from md;
Empty set (0.02 sec)

mysql> insert into md(id,name) values(12,'mudassir');
Query OK, 1 row affected (0.00 sec)

mysql> select * from md;
+------+----------+
| id   | name     |
+------+----------+
|   12 | mudassir |
+------+----------+
1 row in set (0.00 sec)

mysql> insert into md(id,name) values(121,'mudassir1');
Query OK, 1 row affected (0.00 sec)

mysql> insert into md(id,name) values(11,'1mudassir1');
Query OK, 1 row affected (0.00 sec)

mysql> insert into md(id,name) values(151,'1muir12');
Query OK, 1 row affected (0.00 sec)

mysql> insert into md(id,name) values(181,'1muire12');
Query OK, 1 row affected (0.00 sec)

mysql> select * from md;
+------+------------+
| id   | name       |
+------+------------+
|   12 | mudassir   |
|  121 | mudassir1  |
|   11 | 1mudassir1 |
|  151 | 1muir12    |
|  181 | 1muire12   |
+------+------------+
5 rows in set (0.00 sec)

mysql> create table md2(id int(10),name varchar(20));
Query OK, 0 rows affected, 1 warning (0.03 sec)

mysql> select * from md2;
Empty set (0.00 sec)

mysql> insert into md2(id,name) values(181,'1muire12');
Query OK, 1 row affected (0.01 sec)

mysql> insert into md2(id,name) values(181,'1muirfde12');
Query OK, 1 row affected (0.00 sec)

mysql> insert into md2(id,name) values(1481,'1muirfde12');
Query OK, 1 row affected (0.01 sec)

mysql> insert into md2(id,name) values(1481,'1muirfdve12');
Query OK, 1 row affected (0.01 sec)

mysql> insert into md2(id,name) values(1481,'1mui4e12');
Query OK, 1 row affected (0.00 sec)

mysql> insert into md2(id,name) values(1481,'1mui4e1');
Query OK, 1 row affected (0.01 sec)

mysql> select * from md2
    -> ;
+------+-------------+
| id   | name        |
+------+-------------+
|  181 | 1muire12    |
|  181 | 1muirfde12  |
| 1481 | 1muirfde12  |
| 1481 | 1muirfdve12 |
| 1481 | 1mui4e12    |
| 1481 | 1mui4e1     |
+------+-------------+
6 rows in set (0.01 sec)

mysql> select name from md
    -> ;
+------------+
| name       |
+------------+
| mudassir   |
| mudassir1  |
| 1mudassir1 |
| 1muir12    |
| 1muire12   |
+------------+
5 rows in set (0.00 sec)

mysql> select name from md2;
+-------------+
| name        |
+-------------+
| 1muire12    |
| 1muirfde12  |
| 1muirfde12  |
| 1muirfdve12 |
| 1mui4e12    |
| 1mui4e1     |
+-------------+
6 rows in set (0.00 sec)

mysql> select id from md2;
+------+
| id   |
+------+
|  181 |
|  181 |
| 1481 |
| 1481 |
| 1481 |
| 1481 |
+------+
6 rows in set (0.00 sec)

mysql> select name from md2 where 
    -> id is 181;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '181' at line 2
mysql> select name from md2 where  id=181;
+------------+
| name       |
+------------+
| 1muire12   |
| 1muirfde12 |
+------------+
2 rows in set (0.00 sec)

mysql> select name from md2 where  id=181 or id = 1481;
+-------------+
| name        |
+-------------+
| 1muire12    |
| 1muirfde12  |
| 1muirfde12  |
| 1muirfdve12 |
| 1mui4e12    |
| 1mui4e1     |
+-------------+
6 rows in set (0.01 sec)

mysql> select name from md2 where  id=181 or id = 148;
+------------+
| name       |
+------------+
| 1muire12   |
| 1muirfde12 |
+------------+
2 rows in set (0.00 sec)

mysql> select name from md2 where not  id=181 ;
+-------------+
| name        |
+-------------+
| 1muirfde12  |
| 1muirfdve12 |
| 1mui4e12    |
| 1mui4e1     |
+-------------+
4 rows in set (0.00 sec)

mysql> select count(name) from md2;
+-------------+
| count(name) |
+-------------+
|           6 |
+-------------+
1 row in set (0.00 sec)

mysql> select count(name) from md2 where id=181;
+-------------+
| count(name) |
+-------------+
|           2 |
+-------------+
1 row in set (0.00 sec)

mysql> select count(name ) from md2 where not id=181;
+--------------+
| count(name ) |
+--------------+
|            4 |
+--------------+
1 row in set (0.00 sec)

mysql> select avg(id) from md;
+---------+
| avg(id) |
+---------+
| 95.2000 |
+---------+
1 row in set (0.00 sec)

mysql> select sum(id) from md;
+---------+
| sum(id) |
+---------+
|     476 |
+---------+
1 row in set (0.00 sec)

mysql> select sum(id) from md where id=181;
+---------+
| sum(id) |
+---------+
|     181 |
+---------+
1 row in set (0.00 sec)

mysql> select id from md2;
+------+
| id   |
+------+
|  181 |
|  181 |
| 1481 |
| 1481 |
| 1481 |
| 1481 |
+------+
6 rows in set (0.01 sec)

mysql> select avg(id) from md where id=181;
+----------+
| avg(id)  |
+----------+
| 181.0000 |
+----------+
1 row in set (0.01 sec)

mysql> select max(id) from md2;
+---------+
| max(id) |
+---------+
|    1481 |
+---------+
1 row in set (0.00 sec)

mysql> select sum(id) from md2 where id=181;
+---------+
| sum(id) |
+---------+
|     362 |
+---------+
1 row in set (0.00 sec)

mysql> select id from md2 where not id=0 having id > 200;
+------+
| id   |
+------+
| 1481 |
| 1481 |
| 1481 |
| 1481 |
+------+
4 rows in set (0.00 sec)

mysql> history
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'history' at line 1
mysql> insert md2(name) value('md');
Query OK, 1 row affected (0.01 sec)

mysql> insert md2(name) value('mddrg');
Query OK, 1 row affected (0.01 sec)

mysql> insert md2(name) value('mddrrg');
Query OK, 1 row affected (0.00 sec)

mysql> insert md2(name) value('mddrr2g');
Query OK, 1 row affected (0.01 sec)

mysql> insert md2(name) value('mdd2g');
Query OK, 1 row affected (0.01 sec)

mysql> insert md2(name) value('mdd2g23');
Query OK, 1 row affected (0.00 sec)

mysql> select * from md2
    -> ;
+------+-------------+
| id   | name        |
+------+-------------+
|  181 | 1muire12    |
|  181 | 1muirfde12  |
| 1481 | 1muirfde12  |
| 1481 | 1muirfdve12 |
| 1481 | 1mui4e12    |
| 1481 | 1mui4e1     |
| NULL | md          |
| NULL | mddrg       |
| NULL | mddrrg      |
| NULL | mddrr2g     |
| NULL | mdd2g       |
| NULL | mdd2g23     |
+------+-------------+
12 rows in set (0.00 sec)

mysql> select * from md2 where id is null;
+------+---------+
| id   | name    |
+------+---------+
| NULL | md      |
| NULL | mddrg   |
| NULL | mddrrg  |
| NULL | mddrr2g |
| NULL | mdd2g   |
| NULL | mdd2g23 |
+------+---------+
6 rows in set (0.00 sec)

mysql> select * from md2 where id is not null;
+------+-------------+
| id   | name        |
+------+-------------+
|  181 | 1muire12    |
|  181 | 1muirfde12  |
| 1481 | 1muirfde12  |
| 1481 | 1muirfdve12 |
| 1481 | 1mui4e12    |
| 1481 | 1mui4e1     |
+------+-------------+
6 rows in set (0.00 sec)

mysql> update md set id=1 where id is null;
Query OK, 0 rows affected (0.00 sec)
Rows matched: 0  Changed: 0  Warnings: 0

mysql> update md2 set id=1 where id is null;
Query OK, 6 rows affected (0.01 sec)
Rows matched: 6  Changed: 6  Warnings: 0

mysql> select * from md2;
+------+-------------+
| id   | name        |
+------+-------------+
|  181 | 1muire12    |
|  181 | 1muirfde12  |
| 1481 | 1muirfde12  |
| 1481 | 1muirfdve12 |
| 1481 | 1mui4e12    |
| 1481 | 1mui4e1     |
|    1 | md          |
|    1 | mddrg       |
|    1 | mddrrg      |
|    1 | mddrr2g     |
|    1 | mdd2g       |
|    1 | mdd2g23     |
+------+-------------+
12 rows in set (0.00 sec)

mysql> delecte id from md2 where id=181;
mysql> delete from md2 where id=181;
Query OK, 2 rows affected (0.01 sec)

mysql> select * from md2;
+------+-------------+
| id   | name        |
+------+-------------+
| 1481 | 1muirfde12  |
| 1481 | 1muirfdve12 |
| 1481 | 1mui4e12    |
| 1481 | 1mui4e1     |
|    1 | md          |
|    1 | mddrg       |
|    1 | mddrrg      |
|    1 | mddrr2g     |
|    1 | mdd2g       |
|    1 | mdd2g23     |
+------+-------------+
10 rows in set (0.00 sec)

mysql> delecte id from md2 where id=1;
mysql> select * from md2 where id between 0 and 10;
+------+---------+
| id   | name    |
+------+---------+
|    1 | md      |
|    1 | mddrg   |
|    1 | mddrrg  |
|    1 | mddrr2g |
|    1 | mdd2g   |
|    1 | mdd2g23 |
+------+---------+
6 rows in set (0.00 sec)
