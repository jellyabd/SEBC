<html>
<pre>

[root@sb1 245-hive-HIVESERVER2]# kinit -k -t hive.keytab hive/sb1@W.IO
[root@sb1 245-hive-HIVESERVER2]#
[root@sb1 245-hive-HIVESERVER2]#
[root@sb1 245-hive-HIVESERVER2]#
[root@sb1 245-hive-HIVESERVER2]# beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://sb1:10000/default;principal=hive/sb1@W.IO
scan complete in 3ms
Connecting to jdbc:hive2://sb1:10000/default;principal=hive/sb1@W.IO
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ


0: jdbc:hive2://sb1:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170511040707_22fa86e8-3246-430b-94ee-5e30bce9b6f3): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040707_22fa86e8-3246-430b-94ee-5e30bce9b6f3); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20170511040707_22fa86e8-3246-430b-94ee-5e30bce9b6f3): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040707_22fa86e8-3246-430b-94ee-5e30bce9b6f3); Time taken: 0.117 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.2 seconds)


0: jdbc:hive2://sb1:10000/default> create role sentry_admin;
INFO  : Compiling command(queryId=hive_20170511035858_20b4ead5-7d4e-46ec-a978-0cfc389e64ab): create role admin_role
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511035858_20b4ead5-7d4e-46ec-a978-0cfc389e64ab); Time taken: 0.114 seconds
INFO  : Executing command(queryId=hive_20170511035858_20b4ead5-7d4e-46ec-a978-0cfc389e64ab): create role admin_role
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511035858_20b4ead5-7d4e-46ec-a978-0cfc389e64ab); Time taken: 0.105 seconds
INFO  : OK
No rows affected (0.289 seconds)
0: jdbc:hive2://sb1:10000/default> grant all on server sb1 to role sentry_admin;
INFO  : Compiling command(queryId=hive_20170511040000_ee986039-1a27-47c6-9ea8-8ad7b924ac13): grant all on server sb1 to role admin_role
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040000_ee986039-1a27-47c6-9ea8-8ad7b924ac13); Time taken: 0.11 seconds
INFO  : Executing command(queryId=hive_20170511040000_ee986039-1a27-47c6-9ea8-8ad7b924ac13): grant all on server sb1 to role admin_role
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040000_ee986039-1a27-47c6-9ea8-8ad7b924ac13); Time taken: 0.103 seconds
INFO  : OK
No rows affected (0.229 seconds)
0: jdbc:hive2://sb1:10000/default>


0: jdbc:hive2://sb1:10000/default> grant role sentry_admin to group whitelilis;
INFO  : Compiling command(queryId=hive_20170511041212_6a1f2490-6285-4ab8-bbb2-638484b184ed): grant role sentry_admin to group whitelilis
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041212_6a1f2490-6285-4ab8-bbb2-638484b184ed); Time taken: 0.069 seconds
INFO  : Executing command(queryId=hive_20170511041212_6a1f2490-6285-4ab8-bbb2-638484b184ed): grant role sentry_admin to group whitelilis
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041212_6a1f2490-6285-4ab8-bbb2-638484b184ed); Time taken: 0.021 seconds
INFO  : OK
No rows affected (0.106 seconds)


0: jdbc:hive2://sb1:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170511041212_782bf7a9-ad6a-4d5f-9a49-4156cd99b29a): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041212_782bf7a9-ad6a-4d5f-9a49-4156cd99b29a); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20170511041212_782bf7a9-ad6a-4d5f-9a49-4156cd99b29a): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041212_782bf7a9-ad6a-4d5f-9a49-4156cd99b29a); Time taken: 0.203 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| w1         |
| web_logs   |
+------------+--+
5 rows selected (0.3 seconds)


<hr/>
george

[root@sb1 ~]# su - george
[george@sb1 ~]$ kinit george
Password for george@W.IO:
[george@sb1 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1100
Default principal: george@W.IO

Valid starting     Expires            Service principal
05/11/17 04:31:51  05/12/17 04:31:51  krbtgt/W.IO@W.IO
	renew until 05/11/17 04:31:51
[george@sb1 ~]$ beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/sb1@W.IO
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/sb1@W.IO
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170511043232_73bb7184-26ad-4ce7-8813-88386b6393f1): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511043232_73bb7184-26ad-4ce7-8813-88386b6393f1); Time taken: 0.115 seconds
INFO  : Executing command(queryId=hive_20170511043232_73bb7184-26ad-4ce7-8813-88386b6393f1): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511043232_73bb7184-26ad-4ce7-8813-88386b6393f1); Time taken: 0.139 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| w1         |
| web_logs   |
+------------+--+
5 rows selected (0.372 seconds)
0: jdbc:hive2://localhost:10000/default>


<hr/>
ferdinand

[ferdinand@sb1 ~]$ kinit
Password for ferdinand@W.IO:
[ferdinand@sb1 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1200
Default principal: ferdinand@W.IO

Valid starting     Expires            Service principal
05/11/17 04:47:50  05/12/17 04:47:50  krbtgt/W.IO@W.IO
	renew until 05/11/17 04:47:50
[ferdinand@sb1 ~]$ beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline>  !connect jdbc:hive2://localhost:10000/default;principal=hive/sb1@W.IO
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/sb1@W.IO
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20170511044848_d74ce238-a652-47aa-b5e9-a395122960b2): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511044848_d74ce238-a652-47aa-b5e9-a395122960b2); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20170511044848_d74ce238-a652-47aa-b5e9-a395122960b2): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511044848_d74ce238-a652-47aa-b5e9-a395122960b2); Time taken: 0.132 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.323 seconds)
0: jdbc:hive2://localhost:10000/default>

</pre>
<html>
