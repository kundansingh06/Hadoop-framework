# List Files in HDFS


```
hdfs dfs -ls /            List all the files/directories for the given hdfs destination path.

hdfs dfs -ls -d /hadoop   Directories are listed as plain files. In this case, this command will list
the details of hadoop folder.

hdfs dfs -ls -h /data      Format file sizes in a human-readable fashion (eg 64.0m instead of
67108864).

hdfs dfs -ls -R /hadoop    Recursively list all files in hadoop directory and all subdirectories in
hadoop directory.

hdfs dfs -ls /hadoop/dat*   List all the files matching the pattern. In this case, it will list all the
files inside hadoop directory which starts with 'dat'.

```