1. Download and implement the [official MySQL repo](http://dev.mysql.com/downloads/repo/yum/)
    * Enable the repo to install MySQL 5.5
    Download the repo rpm from browser,then
    ```
    for f in $(cat h5); do scp -i ~/.ssh/cloudera.pem /Users/liuzhe/Desktop/mysql57-community-release-el6-11.noarch.rpm   root@$f:/root/  & done
    ```
    On the every remote server 
    ```
    [root@sb1 ~]# rpm -Uvh mysql57-community-release-el6-11.noarch.rpm
    ```
    Edit /etc/yum.repos.d/mysql-community.repo, change the line ```enable=xxx``` to enable mysql5.5, disable others.
    * Install the <code>mysql</code> package on all nodes
    ```
    [root@sb1 ~]# yum install -y mysql
    ```
    * Install <code>mysql-server</code> on the server and replica nodesa ( sb1  and sb2 )
    ```
    [root@sb1 ~]# yum install -y mysql-community-server
    ```
    * Download and copy [the JDBC connector](https://dev.mysql.com/doc/connector-j/5.1/en/connector-j-binary-installation.html) to all nodes.
    ```
    for f in $(cat h5); do scp -i ~/.ssh/cloudera.pem /Users/liuzhe/Downloads/mysql-connector-java-5.0.8.jar    root@$f:/root/  & done
    ```
2. You should not need to build a <code>/etc/my.cnf</code> file to start your MySQL server
    * You will have to modify it to support replication. Check MySQL documentation.<p>
    a. On the master sb1, edit ```/etc/my.conf```, under ```mysqld``` section, add the following
    ```
    server-id = 1
    log_bin = mysql-bin
    ```
    b. On the slave sb2, edit ```/etc/my.conf```, under ```mysqld``` section, add the following
    ```
    server-id = 2
    ```
3. Start the <code>mysqld</code> service.
   On master ```sb1```, start mysql
   ```
   [root@sb1 ~]# service mysqld start
   MySQL Daemon failed to start.
   Starting mysqld:                                           [FAILED]
   ```
   in the ```/var/log/mysqld.log```
   I find 
   ```
   170508 13:32:48 [Note] Server hostname (bind-address): '0.0.0.0'; port: 3306
   170508 13:32:48 [Note]   - '0.0.0.0' resolves to '0.0.0.0';
   170508 13:32:48 [Note] Server socket created on IP: '0.0.0.0'.
   170508 13:32:48 [ERROR] Fatal error: Can't open and lock privilege tables: Table 'mysql.host' doesn't exist
   ```
   To fix it, just do ```mysql_install_db --user=mysql```, and then
   ```service mysqld start``` work fine.
4. Use <code>/usr/bin/mysql_secure_installation</code> to:<br>
    a. Set password protection for the server<br>
    b. Revoke permissions for anonymous users<br>
    c. Permit remote privileged login<br>
    d. Remove test databases<br>
    e. Refresh privileges in memory<br>
    f. Refreshes the <code>mysqld</code> service<p>
5. On the master MySQL node, grant replication privileges for your replica node:<br>
    a. Log in with <code>mysql -u ... -p</code> <br>
    b. Note the FQDN of your replica host.<br>
    c. <code>mysql> **GRANT REPLICATION SLAVE ON \*.\* TO '*user*'@'*FQDN*' IDENTIFIED BY '*password*';**</code><br>
    ```
    GRANT REPLICATION SLAVE ON *.* TO rep@172.31.14.250 IDENTIFIED BY '123456';
    ```
    d. <code>mysql> **SET GLOBAL binlog_format = 'ROW';** </code><br>
    e. <code>mysql> **FLUSH TABLES WITH READ LOCK;</code>**<p>
6. In a second terminal session, log into the MySQL master and show its  status:<br>
    a. <code>mysql> **SHOW MASTER STATUS;**</code><br>
    b. Make note of the file name and byte offset. The replica needs this info to sync to the master.<br>
    ```
    mysql> SHOW MASTER STATUS;
    +------------------+----------+--------------+------------------+
    | File             | Position | Binlog_Do_DB | Binlog_Ignore_DB |
    +------------------+----------+--------------+------------------+
    | mysql-bin.000004 |     1211 |              |                  |
    +------------------+----------+--------------+------------------+
    1 row in set (0.00 sec)
    ```
    c. Logout of the second session; remove the lock on the first with <code>mysql> **UNLOCK TABLES;**</code><p>
7. Login to the replica server and configure a connection to the master:<br>
    <code>mysql> **CHANGE MASTER TO**<br> **MASTER_HOST='*master host*',**<br> **MASTER_USER='*replica user*',**<br> **MASTER_PASSWORD='*replica password*',**<br> **MASTER_LOG_FILE='*master file name*',**<br> **MASTER_LOG_POS=*master file offset*;**</code><p>
    ```
    CHANGE MASTER TO MASTER_HOST='172.31.2.231', MASTER_USER='rep', MASTER_PASSWORD='123456', MASTER_LOG_FILE='mysql-bin.000004', MASTER_LOG_POS=1211
    ```
8. Initiate slave operations on the replica<br>
    a. <code>mysql> **START SLAVE;**</code><br>
    b. <code>mysql> **SHOW SLAVE STATUS \G**</code><br>
    c. If successful, the <code>Slave_IO_State</code> field will read <code>Waiting for master to send event</code><br>
    d. Once successful, capture this output and store it in <code>labs/2_replica_working.md</code><br>
    Here I got:
    <code>

lave_IO_State: Connecting to master
                  Master_Host: 172.31.2.231
                  Master_User: rep
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql-bin.000004
          Read_Master_Log_Pos: 1211
               Relay_Log_File: mysqld-relay-bin.000001
                Relay_Log_Pos: 4
        Relay_Master_Log_File: mysql-bin.000004
             Slave_IO_Running: Connecting
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 1211
              Relay_Log_Space: 107
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: NULL
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 2003
                Last_IO_Error: error connecting to master 'rep@172.31.2.231:3306' - retry-time: 60  retries: 86400
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 0
1 row in set (0.00 sec):
    </code>
    e. Review your log (<code>/var/log/mysqld.log</code>) for errors. If stuck, consult with a colleague or instructor.<p>
    ```
    170508 14:11:36 [Note] Slave SQL thread initialized, starting replication in log 'mysql-bin.000004' at position 1211, relay log './mysqld-relay-bin.000001' position: 4
    170508 14:11:36 [ERROR] Slave I/O: error connecting to master 'rep@172.31.2.231:3306' - retry-time: 60  retries: 86400, Error_code: 2003
    ```
    Try to fix it:
    ```
    [root@sb2 ~]# telnet 172.31.2.231 3306
    Trying 172.31.2.231...
    telnet: connect to address 172.31.2.231: No route to host
    [root@sb2 ~]# ping 172.31.2.231
    PING 172.31.2.231 (172.31.2.231) 56(84) bytes of data.
    64 bytes from 172.31.2.231: icmp_seq=1 ttl=64 time=0.285 ms
    ```
    But on ```sb1```, it work fine.
    ```
    [root@sb1 ~]# telnet sb1 3306
    Trying 172.31.2.231...
    Connected to sb1.
    Escape character is '^]'.
    N
    5.5.56-logj=2}DyT�%HyMU@!!#*Jvmysql_native_passwordConnection closed by foreign host.
```

    After stoping iptables, it works well. 

```
ql> SHOW SLAVE STATUS \G
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: 172.31.2.231
                  Master_User: rep
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql-bin.000004
          Read_Master_Log_Pos: 1211
               Relay_Log_File: mysqld-relay-bin.000002
                Relay_Log_Pos: 253
        Relay_Master_Log_File: mysql-bin.000004
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes
              Replicate_Do_DB:
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                   Last_Error:
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 1211
              Relay_Log_Space: 410
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
               Last_SQL_Error:
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 1
1 row in set (0.00 sec)
```


