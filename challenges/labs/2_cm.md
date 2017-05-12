# List the command and output for ls /etc/yum.repos.d
```
[root@ip-172-31-17-205 yum.repos.d]# ls /etc/yum.repos.d
CentOS-Base.repo  CentOS-Debuginfo.repo  CentOS-Media.repo  CentOS-Vault.repo  cloudera-manager.repo
```

# Connect Cloudera Manager Server to its database
Use the scm_prepare_database.sh script to create the db.properties file
```
[root@ip-172-31-17-205 yum.repos.d]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-29-207.ec2.internal mysql scm root 123456 
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* c
om.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```
