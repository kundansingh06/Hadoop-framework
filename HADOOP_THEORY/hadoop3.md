# What happens if one of the Datanodes gets failed in HDFS?
* Namenode periodically receives a heartbeat and a Block report from each Datanode in the cluster. Every Datanode sends heartbeat message after every 3 seconds to Namenode.
  The health report is just information about a particular Datanode that is working properly or not. In the other words we can say that particular Datanode is alive or not.
* A block report of a particular Datanode contains information about all the blocks on that resides on the corresponding Datanode.
  When Namenode doesn’t receive any heartbeat message for 10 minutes(ByDefault) from a particular Datanode then corresponding Datanode is considered Dead or failed by Namenode.
  Since blocks will be under replicated, the system starts the replication process from one Datanode to another by taking all block information from the Block report of corresponding Datanode.
  The Data for replication transfers directly from one Datanode to another without data passing through Namenode.


![img_2.png](img_2.png)