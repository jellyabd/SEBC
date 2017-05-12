<html>
<h3>The command and output for hdfs dfs -ls /user</h3>
<pre>
[hdfs@p1 ~]$ hdfs dfs -ls /user
Found 3 items
drwxr-xr-x   - chen   chen            0 2017-05-12 03:16 /user/chen
drwxrwxrwx   - mapred hadoop          0 2017-05-12 03:13 /user/history
drwxr-xr-x   - zhou   zhou            0 2017-05-12 03:15 /user/zhou
</pre>
<h3>The command and output from the CM API call ../api/v14/hosts</h3>
<pre>
apple:SEBC liuzhe$ curl -u admin:admin 'http://ec2-52-53-249-77.us-west-1.compute.amazonaws.com:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "31fc6a4a-ed34-4a22-abf6-2d11f7fcf32a",
    "ipAddress" : "172.31.9.183",
    "hostname" : "p1",
    "rackId" : "/default",
    "hostUrl" : "http://p2:7180/cmf/hostRedirect/31fc6a4a-ed34-4a22-abf6-2d11f7fcf32a",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "27325ad1-4fc9-4783-873e-5a7de2b2e2eb",
    "ipAddress" : "172.31.0.72",
    "hostname" : "p2",
    "rackId" : "/default",
    "hostUrl" : "http://p2:7180/cmf/hostRedirect/27325ad1-4fc9-4783-873e-5a7de2b2e2eb",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "3903e16a-a7b7-4abf-968a-3472fab8c4ed",
    "ipAddress" : "172.31.0.20",
    "hostname" : "p3",
    "rackId" : "/default",
    "hostUrl" : "http://p2:7180/cmf/hostRedirect/3903e16a-a7b7-4abf-968a-3472fab8c4ed",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "c5683aee-0e74-4975-af02-28273e0c8e10",
    "ipAddress" : "172.31.7.170",
    "hostname" : "p4",
    "rackId" : "/default",
    "hostUrl" : "http://p2:7180/cmf/hostRedirect/c5683aee-0e74-4975-af02-28273e0c8e10",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  }, {
    "hostId" : "b53cfe87-0d43-4f94-bb12-f021ad50d5de",
    "ipAddress" : "172.31.4.149",
    "hostname" : "p5",
    "rackId" : "/default",
    "hostUrl" : "http://p2:7180/cmf/hostRedirect/b53cfe87-0d43-4f94-bb12-f021ad50d5de",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 15740305408
  } ]
}
</pre>
<h3>The command and output from the CM API call ../api/v6/clusters/<githubName>/services</h3>
<pre>
apple:SEBC liuzhe$ curl -u admin:admin 'http://ec2-52-53-249-77.us-west-1.compute.amazonaws.com:7180/api/v6/clusters/whitelilis/services'
{
  "items" : [ {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://p2:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "STALE",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://p2:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://p2:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://p2:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://p2:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://p2:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "impala",
    "type" : "IMPALA",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://p2:7180/cmf/serviceRedirect/impala",
    "serviceState" : "STOPPED",
    "healthSummary" : "DISABLED",
    "healthChecks" : [ {
      "name" : "IMPALA_ASSIGNMENT_LOCALITY",
      "summary" : "DISABLED"
    }, {
      "name" : "IMPALA_CATALOGSERVER_HEALTH",
      "summary" : "DISABLED"
    }, {
      "name" : "IMPALA_IMPALADS_HEALTHY",
      "summary" : "DISABLED"
    }, {
      "name" : "IMPALA_STATESTORE_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Impala"
  } ]
}
</pre>

</html>
