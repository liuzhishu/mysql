homework

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| cart               |
| information_schema |
| mysql              |
| performance_schema |
| shoppingzz         |
| sys                |
| zhaozhao           |
| zz                 |
+--------------------+
8 rows in set (0.00 sec)

mysql> use zz;
Database changed
mysql> create table dianying(id int primary key auto_increment,name varchar(20) not null,year int(20) not null,daoyan varchar(20) not null,pingfen int(20) not null);
Query OK, 0 rows affected (0.18 sec)

mysql> desc dianying;
+---------+-------------+------+-----+---------+----------------+
| Field   | Type        | Null | Key | Default | Extra          |
+---------+-------------+------+-----+---------+----------------+
| id      | int(11)     | NO   | PRI | NULL    | auto_increment |
| name    | varchar(20) | NO   |     | NULL    |                |
| year    | int(20)     | NO   |     | NULL    |                |
| daoyan  | varchar(20) | NO   |     | NULL    |                |
| pingfen | int(20)     | NO   |     | NULL    |                |
+---------+-------------+------+-----+---------+----------------+
5 rows in set (0.01 sec)

mysql> insert into dianying(name,year,daoyan,pingfen)values('choubi',2018,'liuzhishu',10),('liangxiaowucai',2014,'liuzhishu',0),('lianlianbijiben',2080,'zhaowenyang',5);
Query OK, 3 rows affected (0.14 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from dianying;
+----+-----------------+------+-------------+---------+
| id | name            | year | daoyan      | pingfen |
+----+-----------------+------+-------------+---------+
|  1 | choubi          | 2018 | liuzhishu   |      10 |
|  2 | liangxiaowucai  | 2014 | liuzhishu   |       0 |
|  3 | lianlianbijiben | 2080 | zhaowenyang |       5 |
+----+-----------------+------+-------------+---------+
3 rows in set (0.00 sec)

mysql> select name from dianying where name like 'l%';
+-----------------+
| name            |
+-----------------+
| liangxiaowucai  |
| lianlianbijiben |
+-----------------+
2 rows in set (0.00 sec)

mysql> select year from dianying where year like 2%;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '%' at line 1
mysql> select year from dianying where year like '2%';
+------+
| year |
+------+
| 2018 |
| 2014 |
| 2080 |
+------+
3 rows in set (0.00 sec)

mysql> slect name,daoyan from dianying where daoyan like 'liu%';
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'slect name,daoyan from dianying where daoyan like 'liu%'' at line 1
mysql> select name,daoyan from dianying where daoyan like 'liu%';
+----------------+-----------+
| name           | daoyan    |
+----------------+-----------+
| choubi         | liuzhishu |
| liangxiaowucai | liuzhishu |
+----------------+-----------+
2 rows in set (0.00 sec)

mysql> select name,pingfen from dianying where pingfen=(select max(pingfen) from dianying);
+--------+---------+
| name   | pingfen |
+--------+---------+
| choubi |      10 |
+--------+---------+
1 row in set (0.00 sec)

mysql>![屏幕截图(74)](C:\Users\MI\Pictures\Screenshots\屏幕截图(74).png)

![屏幕截图(75)](C:\Users\MI\Pictures\Screenshots\屏幕截图(75).png)