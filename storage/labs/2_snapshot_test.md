1.  Create a precious directory in HDFS; copy the ZIP course file into it.
```
[hdfs@ip-172-31-27-83 tmp]$ hadoop fs -mkdir /precious
[hdfs@ip-172-31-27-83 tmp]$ hadoop fs -put master.zip /precious
```

2.  Enable snapshots for precious
```
through cm
```

3.  Create a snapshot called sebc-hdfs-test
```
through cm
```

4.  Delete the directory
```
[hdfs@ip-172-31-27-83 tmp]$ hadoop fs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-172-31-17-141.ec2.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has
 snapshots
```

5.  Delete the ZIP file
```
[hdfs@ip-172-31-27-83 tmp]$ hadoop fs -rm /precious/master.zip
```

6.  Restore the deleted file
```
through cm
```

```
[hdfs@ip-172-31-27-83 tmp]$ hadoop fs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup    1261343 2017-05-09 08:27 /precious/master.zip
```

7.  Capture the NameNode web UI screen that lists snapshots in storage/labs/2_snapshot_list.png.
