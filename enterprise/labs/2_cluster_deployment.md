```
[root@ip-172-31-27-83 ~]# curl -X GET -u "hackty:cloudera" http://172.31.27.83:7180/api/v2/cm/deployment
{
  "timestamp" : "2017-05-10T05:47:52.516Z",
  "clusters" : [ {
    "name" : "hackty",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "657457152"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "657457152"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3571397427"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "601"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-27-83.ec2.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "Hive@1014"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-93090ea82772a7209bc2055db662d105",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-07576d2c248c1ccba"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-94775f3f85d39e18946dcd06175a8848",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0dfcd1ca136b4f85a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-a0339082208ee140af873435e56c1a80",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-fd29e13a25367c35b7434101f6aca101",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-04323e26bf1f30a0c"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-fd6252aeaae449fbde871e096321dda7",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0a618924ef88d4be0"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-a0339082208ee140af873435e56c1a80",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5gxns6gauc1k67f7n82v39xjl"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-a0339082208ee140af873435e56c1a80",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7piiexcibsx0e0agu6gbkaf6"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-93090ea82772a7209bc2055db662d105",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-07576d2c248c1ccba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "aj8ihvyfquo5jzhn2sbk1ez44"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-fd29e13a25367c35b7434101f6aca101",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-04323e26bf1f30a0c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "gh5dyg476ox8o8pvts1vy031"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-fd6252aeaae449fbde871e096321dda7",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0a618924ef88d4be0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6eskl16onbq9g8mb6rub8gleh"
          }, {
            "name" : "serverId",
            "value" : "3"
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
          "value" : "ip-172-31-27-83.ec2.internal"
        }, {
          "name" : "database_password",
          "value" : "Hue@1014"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-a0339082208ee140af873435e56c1a80"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-a0339082208ee140af873435e56c1a80",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6uzc9pq9w5ioav3x8ele4e8nw"
          }, {
            "name" : "secret_key",
            "value" : "z2Rzn4OZWmxRp6KnCOD30pOOKCwOcb"
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
            "value" : "ip-172-31-27-83.ec2.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "Oozie@1014"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "657457152"
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
        "name" : "oozie-OOZIE_SERVER-a0339082208ee140af873435e56c1a80",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9oyc6gcselnznpcikifhr6x3f"
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
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "657457152"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
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
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3253"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "657457152"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "4102"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
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
          "value" : "blLE007yPBhX3RBAMUYAyRmF6U9NrB"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-a0339082208ee140af873435e56c1a80",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c8znoj6ri8tlq77amhrt6pakv"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-93090ea82772a7209bc2055db662d105",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-07576d2c248c1ccba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4kgvqz83ws7xg8tt5fk1g1bsk"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-94775f3f85d39e18946dcd06175a8848",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0dfcd1ca136b4f85a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7igymed1uz5xnvc2lpnbbmiou"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-fd29e13a25367c35b7434101f6aca101",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-04323e26bf1f30a0c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6j062lkmfxkg7ypqttfj059mw"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-fd6252aeaae449fbde871e096321dda7",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0a618924ef88d4be0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "c9pqh1ah8dzga4flqj6caqozp"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-a0339082208ee140af873435e56c1a80",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "81"
          }, {
            "name" : "role_jceks_password",
            "value" : "2s9866mqq1vzx98c3vl7s5k4a"
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
            "value" : "657457152"
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
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
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
            "value" : "657457152"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "657457152"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "OLgENQLoxEKk6IxSlyifW4lTEWPRpd"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "ueGzLlbRhrKBAQ11UB8oJKLYXUolWE"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "5yYy31303ezZLYu56Kp9FnDmwn2RFd"
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
        "name" : "hdfs-BALANCER-a0339082208ee140af873435e56c1a80",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-93090ea82772a7209bc2055db662d105",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-07576d2c248c1ccba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e6vtuakj0xfa006yh8kdwxt17"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-94775f3f85d39e18946dcd06175a8848",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0dfcd1ca136b4f85a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bm2o4w01mz752skpp63kwq432"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-fd29e13a25367c35b7434101f6aca101",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-04323e26bf1f30a0c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "327joe5zg88ks6u3nbk3legt3"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-fd6252aeaae449fbde871e096321dda7",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0a618924ef88d4be0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "xaj9n9qhxdhm3h7d3aa6yz7x"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-94775f3f85d39e18946dcd06175a8848",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-0dfcd1ca136b4f85a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bv95k53iw9m2buiqka8e83hg2"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-a0339082208ee140af873435e56c1a80",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "eo6oj2gb7mxmjy9pz7hdi2jlm"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-93090ea82772a7209bc2055db662d105",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-07576d2c248c1ccba"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "989b2lyptib8bluydlmryx8tf"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-fd29e13a25367c35b7434101f6aca101",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-04323e26bf1f30a0c"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2zeggssboxne3ifgkptj1yehh"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-fd6252aeaae449fbde871e096321dda7",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0a618924ef88d4be0"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cv9q00v3kw6l89nckd28b6cja"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-94775f3f85d39e18946dcd06175a8848",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-0dfcd1ca136b4f85a"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "89"
          }, {
            "name" : "role_jceks_password",
            "value" : "6uo69bgurai1wjf9jf21e7vsu"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-a0339082208ee140af873435e56c1a80",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-030ae30ffd9336b86"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "83"
          }, {
            "name" : "role_jceks_password",
            "value" : "9yleqte2nxcl7eue2aaasb9ug"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-030ae30ffd9336b86",
    "ipAddress" : "172.31.17.141",
    "hostname" : "ip-172-31-17-141.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-04323e26bf1f30a0c",
    "ipAddress" : "172.31.19.216",
    "hostname" : "ip-172-31-19-216.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0a618924ef88d4be0",
    "ipAddress" : "172.31.19.226",
    "hostname" : "ip-172-31-19-226.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-07576d2c248c1ccba",
    "ipAddress" : "172.31.27.83",
    "hostname" : "ip-172-31-27-83.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0dfcd1ca136b4f85a",
    "ipAddress" : "172.31.31.221",
    "hostname" : "ip-172-31-31-221.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__7da87e4a-4fcf-407a-ad1a-7c2c72c9e727",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1d2694302543fa29fa27edc90d6bc63dd58358a5efc468d3983bf7cc004aa446",
    "pwSalt" : -7594013631912204409,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-a0339082208ee140af873435e56c1a80",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7f4cd23ed79df2775148a7ff919de1a75d010fc4d0bcbd098664a7bb3060a398",
    "pwSalt" : 8653821932934834620,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-a0339082208ee140af873435e56c1a80",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "952adcaed40ae9df800e00088284189b28102059aea625e9cf3179c63ef61198",
    "pwSalt" : 4522869129063771827,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-a0339082208ee140af873435e56c1a80",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "591108120c943791f8fbeeba636f195fecc04407b42134490c7b3dac4341e66c",
    "pwSalt" : 5272378931397745422,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-a0339082208ee140af873435e56c1a80",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "01ac070a1e51355225aaec955b3c6e2782a0034b3fb472e63506775ee1dfa7be",
    "pwSalt" : 5041871166949671091,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "f2c6b0ef62c74e5c11743e1ce7de4e66c912b1657a80cef205164ad6334cf597",
    "pwSalt" : -4390340877797863525,
    "pwLogin" : true
  }, {
    "name" : "hackty",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "2989ca9719de42b270db6d8d2b0d3b0778921d53d28f24797877edf4626880aa",
    "pwSalt" : 7253801311646389446,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "35c98bd000e6ea5cd0ca8a66069ef12b2b5c93a423ef93a0098eb59a86577ccb",
    "pwSalt" : -3964887768705937080,
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
          "value" : "657457152"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "657457152"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "854589440"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-27-83.ec2.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "reports"
        }, {
          "name" : "headlamp_database_password",
          "value" : "Reports@1014"
        }, {
          "name" : "headlamp_database_user",
          "value" : "reports"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "657457152"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "657457152"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "854589440"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-a0339082208ee140af873435e56c1a80",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-030ae30ffd9336b86"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "74xt26q4hbotsj2wjzz6lw6h2"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-a0339082208ee140af873435e56c1a80",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-030ae30ffd9336b86"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1pidqqapi9glh5n63u9ah34a4"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-a0339082208ee140af873435e56c1a80",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-030ae30ffd9336b86"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "31a928wemldxzfdsw0ufz2vk4"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-a0339082208ee140af873435e56c1a80",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-030ae30ffd9336b86"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5d5ohxufbid10i81lj261pbn1"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-a0339082208ee140af873435e56c1a80",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-030ae30ffd9336b86"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8hpmzsr1xlghldzuqlu9z6xs1"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/22/2012 19:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcel
s/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/,http://34.239.246.157/cdh5.9.2/"    } ]
  }
}
```
