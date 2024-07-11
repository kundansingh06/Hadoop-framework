# Hadoop configuration files

* HADOOP-ENV.sh

It specifies the environment variables that affect the JDK used by Hadoop Daemon (bin/hadoop). Uses to set JRE so one of the environment variable in Hadoop Daemons is $Java_Home.

* CORE-SITE.XML

It informs Hadoop daemons where the NAMENODE runs in the cluster. It also informs the Name Node as to which IP and ports it should bind.

* HDFS-SITE.XML

It contains the configuration settings for Replication factor, Block Size, NAMENODE/DIR, DATANODE/DIR, SECONDARYNODE/DIR. 

* MAPRED-SITE.XML

It contains the configuration settings for MapReduce. In this file, we specify a framework name for MapReduce, by setting the MapReduce.framework.name.

* YARN-SITE.XML:

it contains settings for Node Manager, Resource Manager, Containers, and Application Master.