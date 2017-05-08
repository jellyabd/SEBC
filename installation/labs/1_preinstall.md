1. Check `vm.swappiness` on all your nodes
    * Set the value to `1` if necessary
    ```
    [liuzhe@aws-inf-cloudera1 ~]$ cat /proc/sys/vm/swappiness
    30
    [liuzhe@aws-inf-cloudera1 ~]$ sudo sed -i '$a\vm.swappiness=1' /etc/sysctl.conf
    [liuzhe@aws-inf-cloudera1 ~]$ sudo sysctl -p
    vm.swappiness = 1
    [liuzhe@aws-inf-cloudera1 ~]$ cat /proc/sys/vm/swappiness
    1
    ```
2. Show the mount attributes of your volume(s)
   For aws using xfs, so
   ```
   [liuzhe@aws-inf-cloudera1 ~]$ cat /etc/mtab | grep xfs
   /dev/xvda1 / xfs rw,relatime,attr2,inode64,noquota 0 0
   ```
3. If you have `ext`-based volumes, list the reserve space setting
    * XFS volumes do not support reserve space
    I use ```XFS``` volumes.
4. Disable transparent hugepage support
   Add the following lines into  /etc/rc.local
   ```
   if test -f /sys/kernel/mm/transparent_hugepage/enabled; then
      echo never > /sys/kernel/mm/transparent_hugepage/enabled
   fi
   if test -f /sys/kernel/mm/transparent_hugepage/defrag; then
      echo never > /sys/kernel/mm/transparent_hugepage/defrag
   fi
   ```
   Then,
   ```
   sudo bash /etc/rc.local
   ```
   Then,
   ```
   [liuzhe@aws-inf-cloudera1 ~]$ cat /sys/kernel/mm/transparent_hugepage/enabled
   always madvise [never]
   [liuzhe@aws-inf-cloudera1 ~]$ cat /sys/kernel/mm/transparent_hugepage/defrag
   always madvise [never]
   ```
4. List your network interface configuration
   ```
    uzhe@aws-inf-cloudera1 ~]$ ifconfig
    eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
            inet 172.31.26.170  netmask 255.255.240.0  broadcast 172.31.31.255
            inet6 fe80::9:68ff:fef5:c3ca  prefixlen 64  scopeid 0x20<link>
            ether 02:09:68:f5:c3:ca  txqueuelen 1000  (Ethernet)
            RX packets 1921  bytes 158361 (154.6 KiB)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 1493  bytes 188024 (183.6 KiB)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    
    lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
            inet 127.0.0.1  netmask 255.0.0.0
            inet6 ::1  prefixlen 128  scopeid 0x10<host>
            loop  txqueuelen 0  (Local Loopback)
            RX packets 6  bytes 416 (416.0 B)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 6  bytes 416 (416.0 B)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
   ```
5. Show that forward and reverse host lookups are correctly resolved
  * For `/etc/hosts`, use `getent`
  * For DNS, use `nslookup`
  ```
  [liuzhe@aws-inf-cloudera1 ~]$ for f in 172.31.26.170 aws-inf-cloudera1 172.31.27.46 aws-inf-cloudera2 172.31.28.77 aws-inf-cloudera3 172.31.25.129 aws-inf-cloudera4 172.31.30.61 aws-inf-cloudera5 ; do getent hosts $f; done
  172.31.26.170   aws-inf-cloudera1
  172.31.26.170   aws-inf-cloudera1
  172.31.27.46    aws-inf-cloudera2
  172.31.27.46    aws-inf-cloudera2
  172.31.28.77    aws-inf-cloudera3
  172.31.28.77    aws-inf-cloudera3
  172.31.25.129   aws-inf-cloudera4
  172.31.25.129   aws-inf-cloudera4
  172.31.30.61    aws-inf-cloudera5
  172.31.30.61    aws-inf-cloudera5
  ```
6. Show the <code>nscd</code> service is running
  ```
  [liuzhe@aws-inf-cloudera1 ~]$ service nscd status
  Redirecting to /bin/systemctl status  nscd.service
    nscd.service
     Loaded: not-found (Reason: No such file or directory)
        Active: inactive (dead)
	[liuzhe@aws-inf-cloudera1 ~]$ ps aux | grep nscd
	liuzhe    2251  0.0  0.0 112660   968 pts/0    S+   07:31   0:00 grep --color=auto nscd
	[liuzhe@aws-inf-cloudera1 ~]$ sudo yum install nscd
  ```
  So nscd is not installed, so install it first. After install, start it and check.
  ```
  [liuzhe@aws-inf-cloudera1 ~]$ sudo su -
  上一次登录：五 5月  5 03:15:42 UTC 2017pts/0 上
  [root@aws-inf-cloudera1 ~]# service nscd start
  Redirecting to /bin/systemctl start  nscd.service
  [root@aws-inf-cloudera1 ~]# service nscd status
  Redirecting to /bin/systemctl status  nscd.service
   nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Mon 2017-05-08 07:32:39 UTC; 8s ago
   Process: 2431 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
   Main PID: 2432 (nscd)
  ```
7. Show the <code>ntpd</code> service is running<br>
  ```
  [root@aws-inf-cloudera1 ~]# service ntpd status
  Redirecting to /bin/systemctl status  ntpd.service
   ntpd.service
   Loaded: not-found (Reason: No such file or directory)
   Active: inactive (dead)
   [root@aws-inf-cloudera1 ~]# ps aux | grep ntp
   root      2466  0.0  0.0 112648   960 pts/0    S+   07:37   0:00 grep --color=auto ntp
   [root@aws-inf-cloudera1 ~]# yum install -y ntpd
   ```
   Its name is not ```ntpd``` but  ```ntp```
   ```
   [root@aws-inf-cloudera1 ~]# yum install -y ntp
   ```
   Then start and check
   ```
   [root@aws-inf-cloudera1 ~]# service ntpd start
   Redirecting to /bin/systemctl start  ntpd.service
   [root@aws-inf-cloudera1 ~]# service ntpd status
   Redirecting to /bin/systemctl status  ntpd.service
     ntpd.service - Network Time Service
      Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
         Active: active (running) since Mon 2017-05-08 07:37:51 UTC; 9s ago
   ```
