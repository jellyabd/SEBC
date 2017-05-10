<html>
<pre>
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = W.IO
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 1d
 renew_lifetime = 7d
 forwardable = true

[realms]
 W.IO = {
  kdc = sb5
  admin_server = sb5
 }

[domain_realm]
 .w.io = W.IO
 w.io = W.IO

</pre>
</html>
