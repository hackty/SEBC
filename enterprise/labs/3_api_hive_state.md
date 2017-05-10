1.  stop the Hive service 
```
[root@ip-172-31-27-83 ~]# curl -X POST -u "hackty:cloudera" http://172.31.27.83:7180/api/v12/clusters/hackty/services/hive/commands/stop
{
  "id" : 964,
  "name" : "Stop",
  "startTime" : "2017-05-10T05:57:04.401Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

2.  start the Hive service 
```
[root@ip-172-31-27-83 ~]# curl -X POST -u "hackty:cloudera" http://172.31.27.83:7180/api/v12/clusters/hackty/services/hive/commands/start
{
  "id" : 968,
  "name" : "Start",
  "startTime" : "2017-05-10T05:57:47.640Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

3.  check the current state of the Hive service
```
[root@ip-172-31-27-83 ~]# curl -X GET -u "hackty:cloudera" http://172.31.27.83:7180/api/v12/clusters/hackty/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-27-83.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-27-83.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "STALE",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}
```




