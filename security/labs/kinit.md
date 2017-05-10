<html>

<h3>add user whitelilis as admin</h3>
<pre>
/usr/sbin/kadmin.local -q "addprinc whitelilis/admin"
</pre>

<h3>create ticket</h3>
<pre>
[root@sb5 ~]# kinit whitelilis/admin
Password for whitelilis/admin@W.IO:
</pre>

<h3>check ticket</h3>
<pre>
[root@sb5 ~]# klist -e
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: whitelilis/admin@W.IO

Valid starting     Expires            Service principal
05/10/17 08:38:01  05/11/17 08:38:01  krbtgt/W.IO@W.IO
	renew until 05/10/17 08:38:01, Etype (skey, tkt): aes256-cts-hmac-sha1-96, aes256-cts-hmac-sha1-96
[root@sb5 ~]#
</pre>
