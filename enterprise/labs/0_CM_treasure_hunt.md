1.  What is ubertask optimization?  
mapreduce.job.ubertask.enable  
(Whether to enable ubertask optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.)

2.  Where in CM is the Kerberos Security Realm value displayed?  
Administration->Settings->CATEGORY(Kerberos)

3.  Which CDH service(s) host a property for enabling Kerberos authentication?  
ZooKeeper、YARN、HDFS、Hive、Hue、Oozie、Cloudera Management Service and so on

4.  How do you upgrade the CM agents?  
Hosts->All Hosts->Select all CM agents and click "Re-run Upgrade Wizard" 

5.  Give the tsquery statement used to chart Hue's CPU utilization?  
SELECT cpu_system_rate + cpu_user_rate WHERE entityName = "hue-HUE_SERVER-a0339082208ee140af873435e56c1a80" AND category = ROLE

6.  Name all the roles that make up the Hive service  
HiveServer2、Hive Metastore Server、Gateway、WebHCat Server

7.  What steps must be completed before integrating Cloudera Manager with Kerberos?  
Set up a working KDC. Cloudera Manager supports authentication with MIT KDC and Active Directory.  
Configure the KDC to allow renewable tickets with non-zero ticket lifetimes.
Active Directory allows renewable tickets with non-zero lifetimes by default. You can verify this by checking Domain Security Settings > Account Policies > Kerberos Policy in Active Directory.  
If you are using Active Directory, make sure LDAP over TLS/SSL (LDAPS) is enabled for the Domain Controllers.  
Install the OS-specific packages for your cluster.    
Create an account for Cloudera Manager that has the permissions to create other accounts in the KDC.   
