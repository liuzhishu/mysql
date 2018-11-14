


# HomeWork

- Microsoft Windows [版本 10.0.17134.345]
  (c) 2018 Microsoft Corporation。保留所有权利。

  C:\WINDOWS\system32>mywsql -u root -p
  'mywsql' 不是内部或外部命令，也不是可运行的程序
  或批处理文件。

  C:\WINDOWS\system32>mysql -u root -p
  Enter password: ***********
  Welcome to the MySQL monitor.  Commands end with ; or \g.
  Your MySQL connection id is 41
  Server version: 8.0.12 MySQL Community Server - GPL

  Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

  Oracle is a registered trademark of Oracle Corporation and/or its
  affiliates. Other names may be trademarks of their respective
  owners.

  Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

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
  8 rows in set (0.02 sec)

  mysql> use zhaozhao;
  Database changed
  mysql> create table shoucang(id int primary key auto_increment,name varchar(10));
  Query OK, 0 rows affected (0.19 sec)

  mysql> desc shoucang;
  +-------+-------------+------+-----+---------+----------------+
  | Field | Type        | Null | Key | Default | Extra          |
  +-------+-------------+------+-----+---------+----------------+
  | id    | int(11)     | NO   | PRI | NULL    | auto_increment |
  | name  | varchar(10) | YES  |     | NULL    |                |
  +-------+-------------+------+-----+---------+----------------+
  2 rows in set (0.01 sec)

  mysql> alter table shoucang add shoucangbiao varchar(10);
  Query OK, 0 rows affected (0.11 sec)
  Records: 0  Duplicates: 0  Warnings: 0

  mysql> insert into shoucang(name,shoucangbiao)values('jia','keai'),('yi','wenrou');
  Query OK, 2 rows affected (0.04 sec)
  Records: 2  Duplicates: 0  Warnings: 0

  mysql> select * from shoucang;
  +----+------+--------------+
  | id | name | shoucangbiao |
  +----+------+--------------+
  |  1 | jia  | keai         |
  |  2 | yi   | wenrou       |
  +----+------+--------------+
  2 rows in set (0.00 sec)

  mysql> alter table shoucang drop shoucangbiao;
  Query OK, 0 rows affected (0.62 sec)
  Records: 0  Duplicates: 0  Warnings: 0

  mysql> select * from shoucang;
  +----+------+
  | id | name |
  +----+------+
  |  1 | jia  |
  |  2 | yi   |
  +----+------+
  2 rows in set (0.00 sec)

  mysql>![屏幕截图(73)](C:\Users\MI\Pictures\Screenshots\屏幕截图(73).png)

