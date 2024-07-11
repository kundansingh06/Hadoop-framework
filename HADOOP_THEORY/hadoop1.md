# Hadoop Framework
* Hadoop is a framework (open source) for writing, running, storing, and processing large datasets in a parallel and distributed manner. It is a solution that is used to overcome the challenges faced by big data.

# Hadoop Components
* Common: contains all Java libraries on which all hadoop modules depend
* Hadoop Distributed File System (HDFS): a distributed file system that offers high data access speed and store large amount of data a cross multiple nodes.
* YARN (Yet Another Resource Negotiator): yarn is the clusters manger in hadoop it acts as job scheduler
* MapReduce: it’s a parallel data processing tool that used to process data parallelly across multiple clusters

# Building Blocks of Hadoop:
* Name Node

* Data Node

* Secondary Name Node (SNN)

![img_6.png](img_6.png)

* Job Tracker

* Task Tracker

![img_1.png](img_1.png)

![img_3.png](img_3.png)

![img.png](img.png)


# Basic operations of Namenode:
* Namenode maintains and manages the Data Nodes and assigns the task to them.
* Namenode does not contain actual data of files.
* Namenode stores metadata of actual data like Filename, path, number of data blocks, block IDs, block location, number of replicas and other slave related informations.
* Namenode manages all the request(read, write) of client for actual data file.
* Namenode executes file system name space operations like opening/closing files, renaming files and directories.

# Basic Operations of Datanode:
* Datanodes is responsible of storing actual data.
* Upon instruction from Namenode, it performs operations like creation/replication/deletion of data blocks.
* When one of Datanode gets down then it will not make any effect on Hadoop cluster due to replication.
* All Datanodes are synchronized in the Hadoop cluster in a way that they can communicate with each other for various operations.