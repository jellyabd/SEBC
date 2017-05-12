<html>
<h3>The hostname of your database server</h3>
<pre>
[root@p1 ~]# hostname
p1
</pre>
<h3>The command and output for showing the database server version</h3>
<pre>
[root@p1 up]# mysql -uroot -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 14
Server version: 5.6.36 MySQL Community Server (GPL)

Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.
</pre>
<h3>The command and output for listing the databases created above</h3>
<pre>
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)
</pre>
</html>
