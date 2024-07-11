# Hadoop Distributed File System(HDFS)
* The Hadoop Distributed File System(HDFS) was designed for Big Data Processing.
* It is the core part of Hadoop which is used for data storage.
* It is designed to run on commodity(Low Cost Hardware) hardware.

Feature Of HDFS:-
 * Distributed 
 * Parallel Computation 
 * Replication 
 * Fault Tolerance 
 * Streaming Data Access 
 * Portable: It can easily portable from one platform to other platform

# Hadoop fs vs hdfs dfs
* hadoop fs -> it will point to any filesystem

* hdfs dfs  -> it will point hdfs only


# List Files in HDFS

```
hdfs dfs -ls                     List files in the home HDFS directory.
hdfs dfs -ls /                   List files in the root HDFS directory.
hdfs dfs -ls  /user/hadoop       List files in the /user/hadoop HDFS directory.
hdfs dfs -ls -d  /user/hadoop    Directories are listed as plain files. In this case, this command will list the details of hadoop folder.
hdfs dfs -ls -R  /user/hadoop    Recursively list all files in hadoop directory and all subdirectories in hadoop directory.
hdfs dfs -ls  /user/hadoop/dat*  List all the files matching the pattern. In this case, it will list all the files inside hadoop directory which starts with 'dat'.
```

# File Management in HDFS
```
hdfs dfs -cp     /user/hadoop1/file1  /user/hadoop2        Copying file1 from hadoop1 directory to hadoop2 directory.
hdfs dfs -cp -f  /user/hadoop1/file1  /user/hadoop2        Copies file from source to destination on HDFS. Passing -f overwrites the destination if it already exists.

hdfs dfs -mv /user/hadoop1/file1  /user/hadoop2            Copying file1 from hadoop1 directory to hadoop2 directory and it will deleted from source dircetory.     

hdfs dfs -rm /user/hadoop/file1         Deletes the file (sends it to the trash).
hdfs dfs -rm -r /user/hadoop            Deletes the directory and any content under it recursively.
hdfs dfs -rm -R /user/hadoop            Deletes the directory and any content under it recursively.
hdfs dfs -rmr   /user/hadoop            Deletes the directory and any content under it recursively.
hdfs dfs -rm -skipTrash /user/hadoop    The -skipTrash option will bypass trash, if enabled, and delete the specified file(s) immediately.
hdfs dfs -rmdir /user/hadoop            Delete a directory.

hdfs dfs -mkdir /user/hadoop2           Create a directory in specified HDFS location.
hdfs dfs -mkdir -f /user/hadoop2        Create a directory in specified HDFS location. This command does not fail even if the directory already exists.

```

# Read/Write Files
```
hdfs dfs -touchz /user/hadoop3/kundan.txt   Creates a file kundan.txt under directory /user/hadoop3

hdfs dfs -cat /user/hadoop3/kundan.txt     This command will display the content of the HDFS file kundan.txt on your stdout .

hdfs dfs -text /hadoop/derby.log    HDFS Command that takes a source file and outputs the file in text format on the terminal. The allowed formats are zip and TextRecordInputStream.
hdfs dfs -appendToFile /home/ubuntu/test1   /hadoop/text2 Appends the content of a local file test1 to a hdfs file test2.
```