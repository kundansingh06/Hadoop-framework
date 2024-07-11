# Hadoop Distributed File System(HDFS)
* The Hadoop Distributed File System(HDFS) was designed for Big Data Processing.
* It is the core part of Hadoop which is used for data storage.
* It is designed to run on commodity(Low Cost Hardware) hardware.

Feature Of HDFS:-
 * Distributed Storage & Parallel Computation :Data is stored in distributed manner i.e. various Datanodes are responsible for storing the data.
 * Replication: HDFS provides Replication because of which no fear of Data Loss.
 * High Availability and fault tolerance: HDFS also provides high availability and fault tolerance.
 * Scaleup or Scaledown: Provides scalability to scaleup or scaledown nodes as per our requirement. 
 * Portable: It can easily portable from one platform to other platform 
 * Streaming Data Access


# Hadoop fs vs hdfs dfs
* hadoop fs -> it will point to any filesystem.

* hdfs dfs  -> it will point hdfs only.


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

# Disc Usage
```
*  summary of the amount of disk usage of all files/directories in the path
hdfs dfs -du [-s] [-h] URI [URI …]

hdfs dfs -du /user/hadoop/        Show all individual file and amount of space(in bytes) for each individual file under directory /user/hadoop/
hdfs dfs -du -s /user/hadoop/     Rather than showing the size of each individual file its shows the total (summary) size.
o/p-   20189 20189  /user/hadoop

Note: hdfs dfs -dus /user/hadoop: officially deprecated in 2.6.0->dus is deprcated place of dus we should use below command

hdfs dfs -du  -s -h /hadoop/file  Rather than showing the size of each individual file its shows the total (summary) size. Formats the sizes of files in a human-readable fashion.
o/p-   19.7K 19.7K /user/hadoop


* shows the capacity, size, and free space available on the HDFS file system.
hdfs dfs -df /user/hadoop/        Shows the capacity, free and used space of the filesystem.
hdfs dfs -df -h /user/hadoop/     Shows the capacity, free and used space of the filesystem. -h parameter Formats the sizes of files in a human-readable fashion.
Filesystem        Size     Used     Available  Use%
hdfs://XXXXXXXX   305.4 T  255.2 T     50.1 T   84%



hdfs dfs -count <dir>
-count [-q] [-h] [-v] [-t [<storage type>]] [-u] <path> 
  Count the number of directories, files and bytes under the paths
  that match the specified file pattern.  The output columns are:
  DIR_COUNT FILE_COUNT CONTENT_SIZE PATHNAME
  or, with the -q option:
  QUOTA REM_QUOTA SPACE_QUOTA REM_SPACE_QUOTA
        DIR_COUNT FILE_COUNT CONTENT_SIZE PATHNAME
```


# Upload/Download Files
```
* copyFromLocal (or) put: To copy files/folders from local file system to hdfs store. Local filesystem means the files present on the OS.using -f option with put command will overwrite it.
hdfs dfs -copyFromLocal /user/Desktop/AI.txt   /user/hadoop
(OR)
hdfs dfs -put -f  /user/Desktop/AI.txt   /user/hadoop


* copyToLocal (or) get: To copy files/folders from hdfs store to local file system.
hdfs dfs -copyToLocal  /user/hadoop/myfile.txt  /user/Desktop/  
(OR)
hdfs dfs -get  /user/hadoop/myfile.txt  /user/Desktop/


* Works similarly to the put command, except that the source is deleted after it's copied.
hdfs dfs -moveFromLocal <local src>   <dest(on hdfs)> 
```

# Yarn Logs
```
yarn application -list                                                 : List all running applications.
yarn application -kill   <application_id>                              : Kill a running application.
yarn application -status <application_id>                              : Get the status of a specific application.
yarn application -logs   <application_id>                              : View the logs of a specific application.
yarn logs -applicationId application_id > appID_1432041223735_0001.log : Download the logs 
```