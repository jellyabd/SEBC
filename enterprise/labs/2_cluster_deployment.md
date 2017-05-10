<html>
<pre>
{
  "timestamp" : "2017-05-10T03:18:12.646Z",
  "clusters" : [ {
    "name" : "whitelilis",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "229638144"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "229638144"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "2"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "1064199782"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "179"
          }, {
            "name" : "role_config_suppression_hiveserver2_spark_executor_cores",
            "value" : "true"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "sb1"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-3f945a71e824edd1754bd4d4b2f37fdd",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c83744f0-bca0-4f13-a2f5-47e09baa7982"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-59b1729ddd37dcd67ae4cbbab5643d6e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f0b24ed0-7e1f-44ad-88e0-7fe99d1cfcc1"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-82e1039821213cbd7a901d414a676088",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-83342376ff51f9dad327aba3d0430b6e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "66f21519-01ba-45f2-b296-a23c5cea65f5"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-f3fb6a64c121495e0effb27b57a312fe",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "a13a56e9-5f22-4e34-816d-78abcc71d38e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-82e1039821213cbd7a901d414a676088",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7donw2hxvnq3n3ecwfwfpg73u"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-82e1039821213cbd7a901d414a676088",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "71l7vh9wm1oqbf9lggsqxekz1"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "229638144"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-59b1729ddd37dcd67ae4cbbab5643d6e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "f0b24ed0-7e1f-44ad-88e0-7fe99d1cfcc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "czummndhj4v8jq31vl8xndsuc"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-82e1039821213cbd7a901d414a676088",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d19qbn8n72ci2c0na1rdj2vkx"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-83342376ff51f9dad327aba3d0430b6e",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "66f21519-01ba-45f2-b296-a23c5cea65f5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9v7int61t7sb7691jv89fe4n7"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "sb1"
        }, {
          "name" : "database_password",
          "value" : "huepassword"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-3f945a71e824edd1754bd4d4b2f37fdd"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-82e1039821213cbd7a901d414a676088",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6ycww7hkdm3ssb2y77lygvatl"
          }, {
            "name" : "secret_key",
            "value" : "iaLMCp5M9g9ys34nb6Za1SEw5ZUtCW"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "sb1"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "229638144"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-82e1039821213cbd7a901d414a676088",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7trq90snzyuuvy29w160vdvpp"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "4"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "229638144"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "node_manager_java_heapsize",
            "value" : "962592768"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "1600"
          }, {
            "name" : "rm_io_weight",
            "value" : "800"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "1"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "1024"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "229638144"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "1024"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "1"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "80"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "LRC0E15ZEzVi1ujSSwhboKVirHsT4d"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-82e1039821213cbd7a901d414a676088",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eav1jhr49mr6u3w8me18vdq9z"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3f945a71e824edd1754bd4d4b2f37fdd",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c83744f0-bca0-4f13-a2f5-47e09baa7982"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8m0cim9c3g5owz7ji9jjt65a5"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-59b1729ddd37dcd67ae4cbbab5643d6e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "f0b24ed0-7e1f-44ad-88e0-7fe99d1cfcc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7avn8p4grmpyklr497z38f4ug"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-83342376ff51f9dad327aba3d0430b6e",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "66f21519-01ba-45f2-b296-a23c5cea65f5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cccj95t0471l8jzgw4brcegvf"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-f3fb6a64c121495e0effb27b57a312fe",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "a13a56e9-5f22-4e34-816d-78abcc71d38e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6hlt7gkw0zjjivm0zt60cgx92"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-82e1039821213cbd7a901d414a676088",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "54"
          }, {
            "name" : "role_jceks_password",
            "value" : "dgjiyzfx7c9zw3fk391fz9fb0"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "229638144"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3170683699"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "400"
          }, {
            "name" : "rm_io_weight",
            "value" : "200"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "2147483648"
          }, {
            "name" : "role_config_suppression_namenode_java_heapsize_minimum_validator",
            "value" : "true"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "2147483648"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "PWxNJNqEqyiMxpWnt8UtUrCUuphbyZ"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "Knnw7L9abJGiE7M7nCQPDLdmi0DO5o"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "ledFfSQ76gs0d6XS2A8y53CVzcDHLj"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "20"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-82e1039821213cbd7a901d414a676088",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-3f945a71e824edd1754bd4d4b2f37fdd",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c83744f0-bca0-4f13-a2f5-47e09baa7982"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e6jqbjcye6a2c6bqgsiych7ll"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-59b1729ddd37dcd67ae4cbbab5643d6e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "f0b24ed0-7e1f-44ad-88e0-7fe99d1cfcc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dmbk1n42z52u6u9ymnlt8gzmi"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-83342376ff51f9dad327aba3d0430b6e",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "66f21519-01ba-45f2-b296-a23c5cea65f5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1mypry1yjdn9i45qu215ec3ks"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-f3fb6a64c121495e0effb27b57a312fe",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "a13a56e9-5f22-4e34-816d-78abcc71d38e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6savg8edf7uumv3ji7j5jr555"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-3f945a71e824edd1754bd4d4b2f37fdd",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "c83744f0-bca0-4f13-a2f5-47e09baa7982"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "66vp1rgfh3tyugxe7tatsz68g"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-82e1039821213cbd7a901d414a676088",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "namenode_id",
            "value" : "57"
          }, {
            "name" : "role_jceks_password",
            "value" : "17lng6xcucjmiib1kgwbx6tmr"
          } ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-82e1039821213cbd7a901d414a676088",
        "type" : "SECONDARYNAMENODE",
        "hostRef" : {
          "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1488uuzzq6y8my7wot4690et6"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de",
    "ipAddress" : "172.31.2.231",
    "hostname" : "sb1",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "f0b24ed0-7e1f-44ad-88e0-7fe99d1cfcc1",
    "ipAddress" : "172.31.14.250",
    "hostname" : "sb2",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "66f21519-01ba-45f2-b296-a23c5cea65f5",
    "ipAddress" : "172.31.5.190",
    "hostname" : "sb3",
    "rackId" : "/default",
    "config" : {
      "items" : [ {
        "name" : "host_config_suppression_memory_overcommitted_validator",
        "value" : "true"
      } ]
    }
  }, {
    "hostId" : "a13a56e9-5f22-4e34-816d-78abcc71d38e",
    "ipAddress" : "172.31.9.37",
    "hostname" : "sb4",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "c83744f0-bca0-4f13-a2f5-47e09baa7982",
    "ipAddress" : "172.31.5.227",
    "hostname" : "sb5",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-82e1039821213cbd7a901d414a676088",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "de9de2791531bfd93e498cfa391df682185b8bb16e4ec22dce06ab49a639473b",
    "pwSalt" : -41071886055436769,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-82e1039821213cbd7a901d414a676088",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "b5d8aa81c2b158467fbf9d295b53747358d4d343d6090b986be6496ad23fef47",
    "pwSalt" : 2414057797681535204,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-82e1039821213cbd7a901d414a676088",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c6b13cdc3c3aec6feb1304b02cdce5d4caa7ff935a12c0156ccd025acba72bf4",
    "pwSalt" : -3232371528912971023,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-82e1039821213cbd7a901d414a676088",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "b455b3819476a8f004972de37f0ad1e5b7057c8d137c6351da26ff989b85d4d0",
    "pwSalt" : -4991663761100922777,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "07566fb564d9e4012e750102f6f71e0327fa8e20a287680e0f052b534412fb71",
    "pwSalt" : -7231810202227346071,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "e73730968a400ff4e3e27db8cffcdfb18054cd1bda86b470451a6e16d108f501",
    "pwSalt" : -546880055807422320,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.9.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170330-1814",
    "gitHash" : "822da28bff818f57fc1bfc3eafe3a550300ef1b0",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "229638144"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "268435456"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "sb1"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "268435456"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "268435456"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-82e1039821213cbd7a901d414a676088",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1plx4w3ynbj0kqngp7tyijl4y"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-82e1039821213cbd7a901d414a676088",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ao8rzmzhb955crgb76mu3iips"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-82e1039821213cbd7a901d414a676088",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bvak77yiuodt06lgbwqmrl0y"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-82e1039821213cbd7a901d414a676088",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "eti4vzyzbdffqcnc14r75fc00"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-82e1039821213cbd7a901d414a676088",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "070b43c3-2711-4cdb-8f57-d906a44f08de"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ckrhc0pkg7tkaakuic81fmt3t"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/21/2012 8:20"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
</pre>
</html>

