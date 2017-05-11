1.  Verify user privileges
```
[testuser@ip-172-31-27-83 ~]$ kinit
Password for testuser@HACKTY.COM: 
[testuser@ip-172-31-27-83 ~]$ beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511034242_13142ffe-4448-4ad3-9198-7cbc5b64fc5a): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511034242_13142ffe-4448-4ad3-9198-7cbc5b64fc5a); Time taken: 0.419 seconds
INFO  : Executing command(queryId=hive_20170511034242_13142ffe-4448-4ad3-9198-7cbc5b64fc5a): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511034242_13142ffe-4448-4ad3-9198-7cbc5b64fc5a); Time taken: 0.277 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.096 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> 
```

2.  Create a Sentry role with full authorization
```
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170511034747_0f82e32c-a9bb-4e1a-8d68-bd662ce433f7): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511034747_0f82e32c-a9bb-4e1a-8d68-bd662ce433f7); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20170511034747_0f82e32c-a9bb-4e1a-8d68-bd662ce433f7): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511034747_0f82e32c-a9bb-4e1a-8d68-bd662ce433f7); Time taken: 0.155 seconds
INFO  : OK
No rows affected (0.245 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170511034848_fbfc8914-ce47-44e5-ad16-c9dc73190177): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511034848_fbfc8914-ce47-44e5-ad16-c9dc73190177); Time taken: 0.121 seconds
INFO  : Executing command(queryId=hive_20170511034848_fbfc8914-ce47-44e5-ad16-c9dc73190177): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511034848_fbfc8914-ce47-44e5-ad16-c9dc73190177); Time taken: 0.099 seconds
INFO  : OK
No rows affected (0.235 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> GRANT ROLE sentry_admin TO GROUP testuser;
INFO  : Compiling command(queryId=hive_20170511034949_e438c346-6e56-4d99-bc5b-c6f5de3de3f2): GRANT ROLE sentry_admin TO GROUP testuser
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511034949_e438c346-6e56-4d99-bc5b-c6f5de3de3f2); Time taken: 0.087 seconds
INFO  : Executing command(queryId=hive_20170511034949_e438c346-6e56-4d99-bc5b-c6f5de3de3f2): GRANT ROLE sentry_admin TO GROUP testuser
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511034949_e438c346-6e56-4d99-bc5b-c6f5de3de3f2); Time taken: 0.093 seconds
INFO  : OK
No rows affected (0.196 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511035050_b32d6936-ee97-41c2-bc6e-1b97215c9854): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511035050_b32d6936-ee97-41c2-bc6e-1b97215c9854); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20170511035050_b32d6936-ee97-41c2-bc6e-1b97215c9854): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511035050_b32d6936-ee97-41c2-bc6e-1b97215c9854); Time taken: 0.16 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.31 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> 
```

3.  Create additional test users
```
[root@ip-172-31-27-83 ~]# sudo groupadd selector
[root@ip-172-31-27-83 ~]# sudo groupadd inserters
[root@ip-172-31-27-83 ~]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-27-83 ~]# sudo useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-27-83 ~]# kadmin.local
Authenticating as principal root/admin@HACKTY.COM with password.
kadmin.local:  add_principal george
WARNING: no policy specified for george@HACKTY.COM; defaulting to no policy
Enter password for principal "george@HACKTY.COM": 
Re-enter password for principal "george@HACKTY.COM": 
Principal "george@HACKTY.COM" created.
kadmin.local:  add_principal ferdinand
WARNING: no policy specified for ferdinand@HACKTY.COM; defaulting to no policy
Enter password for principal "ferdinand@HACKTY.COM": 
Re-enter password for principal "ferdinand@HACKTY.COM": 
Principal "ferdinand@HACKTY.COM" created.
kadmin.local:  exit
```

4. Create test roles
```
beeline> [root@ip-172-31-27-83 ~]# su testuser
[testuser@ip-172-31-27-83 root]$ beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20170511035757_2ac9a3ec-31e9-4239-b3ed-ceb900d73232): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511035757_2ac9a3ec-31e9-4239-b3ed-ceb900d73232); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20170511035757_2ac9a3ec-31e9-4239-b3ed-ceb900d73232): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511035757_2ac9a3ec-31e9-4239-b3ed-ceb900d73232); Time taken: 0.051 seconds
INFO  : OK
No rows affected (0.186 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20170511035757_78eaa7dd-0268-44cd-a0f1-d87f5338aa1d): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511035757_78eaa7dd-0268-44cd-a0f1-d87f5338aa1d); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20170511035757_78eaa7dd-0268-44cd-a0f1-d87f5338aa1d): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511035757_78eaa7dd-0268-44cd-a0f1-d87f5338aa1d); Time taken: 0.035 seconds
INFO  : OK
No rows affected (0.115 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> 
```

5.  Grant read privilege for all tables to reads
```
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20170511040303_36f8bf6b-f79f-4580-b1a5-88defc00e811): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040303_36f8bf6b-f79f-4580-b1a5-88defc00e811); Time taken: 0.089 seconds
INFO  : Executing command(queryId=hive_20170511040303_36f8bf6b-f79f-4580-b1a5-88defc00e811): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040303_36f8bf6b-f79f-4580-b1a5-88defc00e811); Time taken: 0.061 seconds
INFO  : OK
No rows affected (0.163 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20170511040303_9e2e1242-7f43-47fd-849d-e1291571d148): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040303_9e2e1242-7f43-47fd-849d-e1291571d148); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20170511040303_9e2e1242-7f43-47fd-849d-e1291571d148): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040303_9e2e1242-7f43-47fd-849d-e1291571d148); Time taken: 0.036 seconds
INFO  : OK
No rows affected (0.114 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> 
```

6.  Grant read privilege for default.sample07 only to 'writes':
```
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20170511040303_47729cc3-24b0-4d78-bda7-02292b815316): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040303_47729cc3-24b0-4d78-bda7-02292b815316); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20170511040303_47729cc3-24b0-4d78-bda7-02292b815316): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040303_47729cc3-24b0-4d78-bda7-02292b815316); Time taken: 0.095 seconds
INFO  : OK
No rows affected (0.174 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20170511040404_f1bc6566-8d58-4c1c-929a-d6e12d3d48b9): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040404_f1bc6566-8d58-4c1c-929a-d6e12d3d48b9); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20170511040404_f1bc6566-8d58-4c1c-929a-d6e12d3d48b9): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040404_f1bc6566-8d58-4c1c-929a-d6e12d3d48b9); Time taken: 0.046 seconds
INFO  : OK
No rows affected (0.13 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20170511040404_f7a05b1f-f2ec-4f7b-93f1-eaf5d8d3e2d8): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040404_f7a05b1f-f2ec-4f7b-93f1-eaf5d8d3e2d8); Time taken: 0.057 seconds
INFO  : Executing command(queryId=hive_20170511040404_f7a05b1f-f2ec-4f7b-93f1-eaf5d8d3e2d8): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040404_f7a05b1f-f2ec-4f7b-93f1-eaf5d8d3e2d8); Time taken: 0.03 seconds
INFO  : OK
No rows affected (0.103 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> 
```

7.  kinit as george, then login to beeline  

```
[root@ip-172-31-27-83 ~]# kinit george
Password for george@HACKTY.COM: 
[root@ip-172-31-27-83 ~]# beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511040606_d8ed50ab-18ee-4ebe-b44d-89cc08924a19): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040606_d8ed50ab-18ee-4ebe-b44d-89cc08924a19); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20170511040606_d8ed50ab-18ee-4ebe-b44d-89cc08924a19): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040606_d8ed50ab-18ee-4ebe-b44d-89cc08924a19); Time taken: 0.179 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.36 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> 
```
Repeat the process as ferdinand
```
[root@ip-172-31-27-83 ~]# kinit ferdinand
Password for ferdinand@HACKTY.COM: 
[root@ip-172-31-27-83 ~]# beeline
Beeline version 1.1.0-cdh5.9.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-17-141.ec2.internal:10000/default;principal=hive/ip-172-31-17-141.ec2.internal@HACKTY.COM
Connected to: Apache Hive (version 1.1.0-cdh5.9.2)
Driver: Hive JDBC (version 1.1.0-cdh5.9.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511040808_321d5792-d27a-4ae6-bc21-960c57feab45): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511040808_321d5792-d27a-4ae6-bc21-960c57feab45); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20170511040808_321d5792-d27a-4ae6-bc21-960c57feab45): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511040808_321d5792-d27a-4ae6-bc21-960c57feab45); Time taken: 0.144 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.319 seconds)
0: jdbc:hive2://ip-172-31-17-141.ec2.internal> 
```
