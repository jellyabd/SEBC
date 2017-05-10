<html>

<h3>Report the latest available version of the API</h3>
<pre>
apple:labs liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/version'
v16
</pre>
<hr/>

<h3>Report the CM version</h3>
<pre>
apple:labs liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/v1/cm/version'
{
  "version" : "5.11.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170412-1249",
  "gitHash" : "70cb1442626406432a6e7af5bdf206a384ca3f98",
  "snapshot" : false
}
</pre>
<hr/>

<h3>List all CM users</h3>
<pre>
apple:labs liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/v1/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
</pre>
<hr/>

<h3>Report the database server in use by CM</h3>
<pre>
apple:labs liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/v16/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
</pre>
<hr/>
</html>
