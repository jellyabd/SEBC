<html>
<pre>
[root@p2 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h p1 -utemp -ptemp --scm-host p2 scm scm scm_passwd
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
[                          main] DbProvisioner                  ERROR Exception when creating/dropping database with user 'temp' and jdbc url 'jdbc:mysql://p1/?useUnicode=true&characterEncoding=UTF-8'
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
[                          main] DbProvisioner                  ERROR Stack Trace:
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
--> Error 1, giving up (use --force if you wish to ignore the error)
[root@p2 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql --force -h p1 -utemp -ptemp --scm-host p2 scm scm scm_passwd
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
[                          main] DbProvisioner                  ERROR Exception when creating/dropping database with user 'temp' and jdbc url 'jdbc:mysql://p1/?useUnicode=true&characterEncoding=UTF-8'
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
[                          main] DbProvisioner                  ERROR Stack Trace:
java.sql.SQLException: Can't create database 'scm'; database exists
	at com.mysql.jdbc.SQLError.createSQLException(SQLError.java:964)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3973)
	at com.mysql.jdbc.MysqlIO.checkErrorPacket(MysqlIO.java:3909)
	at com.mysql.jdbc.MysqlIO.sendCommand(MysqlIO.java:2527)
	at com.mysql.jdbc.MysqlIO.sqlQueryDirect(MysqlIO.java:2680)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2486)
	at com.mysql.jdbc.ConnectionImpl.execSQL(ConnectionImpl.java:2444)
	at com.mysql.jdbc.StatementImpl.executeInternal(StatementImpl.java:845)
	at com.mysql.jdbc.StatementImpl.execute(StatementImpl.java:745)
	at com.cloudera.enterprise.dbutil.DbProvisioner.executeSql(DbProvisioner.java:286)
	at com.cloudera.enterprise.dbutil.DbProvisioner.doMain(DbProvisioner.java:95)
	at com.cloudera.enterprise.dbutil.DbProvisioner.main(DbProvisioner.java:110)
--> Error 1, ignoring (because force flag is set)
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
</pre>
</html>
