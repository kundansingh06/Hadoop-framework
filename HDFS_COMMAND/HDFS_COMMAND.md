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
hdfs dfs -cp  /user/hadoop1/file1  /user/hadoop2        Copying file1 from hadoop1 directory to hadoop2 directory.
hdfs dfs -cp -f  /user/hadoop1/file1  /user/hadoop2     Copies file from source to destination on HDFS. Passing -f overwrites the destination if it already exists.

hdfs dfs -mv /user/hadoop1/file1  /user/hadoop2         Move files that match the specified file pattern <src> to a destination <dst>. When moving multiple files, the destination must be a directory.

hdfs dfs -rm /user/hadoop/file1         Deletes the file (sends it to the trash).
hdfs dfs -rm -r /user/hadoop            Deletes the directory and any content under it recursively.
hdfs dfs -rm -R /user/hadoop            Deletes the directory and any content under it recursively.
hdfs dfs -rmr   /user/hadoop            Deletes the directory and any content under it recursively.
hdfs dfs -rm -skipTrash /user/hadoop    The -skipTrash option will bypass trash, if enabled, and delete the specified file(s) immediately.
hdfs dfs -rmdir /user/hadoop            Delete a directory.

hdfs dfs -mkdir /user/hadoop2           Create a directory in specified HDFS location.
hdfs dfs -mkdir -f /user/hadoop2        Create a directory in specified HDFS location. This command does not fail even if the directory already exists.

hdfs dfs -touchz /user/hadoop3          Creates a file of zero length at <path> with current time as the timestamp of that <path>.
```