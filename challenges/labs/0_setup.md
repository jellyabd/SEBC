<html>
<h3>List the cloud provider you are using (AWS, GCE, Azure, other)</h3>
AWS
<h3>List your instances by their IP address and DNS name</h3>
<table>
<tr><td>Ip</td><td>hostname</td><td>Dns used outside</td></tr>
<tr><td>172.31.9.183</td> <td>p1</td>      <td>ec2-52-53-237-23.us-west-1.compute.amazonaws.com</td></tr>
<tr><td><tr>172.31.0.72</td>  <td>p2</td>  <td>ec2-52-53-249-77.us-west-1.compute.amazonaws.com</td></tr>
<tr><td>172.31.0.20</td>  <td>p3</td>      <td>ec2-54-67-0-246.us-west-1.compute.amazonaws.com</td></tr>
<tr><td>172.31.7.170</td> <td>p4</td>      <td>ec2-54-183-169-16.us-west-1.compute.amazonaws.com</td></tr>
<tr><td>172.31.4.149</td> <td>p5</td>      <td>ec2-54-67-124-49.us-west-1.compute.amazonaws.com</td></tr>
</table>
<h3>List the Linux release you are using</h3>
<pre>
[root@p1 etc]# cat /etc/system-release
CentOS release 6.5 (Final)
</pre>
<h3>List the file system capacity for the first node</h3>
<pre>
[root@p1 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        30G  792M   28G   3% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
</pre>

<h3>List the command and output for yum repolist enabled</h3>
<pre>
[root@p1 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirrors.sonic.net
 * extras: mirrors.kernel.org
 * updates: ftp.osuosl.org
base                                                                                                                                                          | 3.7 kB     00:00
extras                                                                                                                                                        | 3.4 kB     00:00
updates                                                                                                                                                       | 3.4 kB     00:00
repo id                                                                           repo name                                                                                    status
base                                                                              CentOS-6 - Base                                                                              6,706
extras                                                                            CentOS-6 - Extras                                                                               64
updates                                                                           CentOS-6 - Updates                                                                             270
repolist: 7,040
</pre>
</html>
