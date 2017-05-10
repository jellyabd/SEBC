<html>
<h3>Show clusters</h3>
<pre>
apple:~ liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/v1/clusters'
{
  "items" : [ {
    "name" : "whitelilis",
    "version" : "CDH5"
  } ]
}
</pre>
<hr/>

<h3>Show hive status</h3>
<pre>
}apple:~ liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/v1/clusters/whitelilis/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://sb1:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : true
}
</pre>
<hr/>

<h3>Stop hive and check it</h3>
<pre>
apple:~ liuzhe$ curl -X POST -u admin:admin 'http://54.193.24.155:7180/api/v1/clusters/whitelilis/services/hive/commands/stop'
{
  "id" : 247,
  "name" : "Stop",
  "startTime" : "2017-05-10T03:34:23.254Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
</pre>

<pre>
apple:~ liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/v1/clusters/whitelilis/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://sb1:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED"
  } ],
  "configStale" : false
}
</pre>
<hr/>

<h3>Start hive and check it</h3>
<pre>
}apple:~ liuzhe$ curl -X POST -u admin:admin 'http://54.193.24.155:7180/api/v1/clusters/whitelilis/services/hive/commands/start'
{
  "id" : 251,
  "name" : "Start",
  "startTime" : "2017-05-10T03:39:04.399Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
</pre>

<pre>
apple:~ liuzhe$ curl -u admin:admin 'http://54.193.24.155:7180/api/v1/clusters/whitelilis/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://sb1:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false
}
</pre>
