# Youtube_Analysis_Hadoop
Youtube data analysis with hadoop on an Azure VM

Azure VM:
Setup an Azure VM to install Hadoop as Windows doesn't have Native IO support thus creating a fresh environment for testing is a safer option. The VM needs Java 8 JRE and JDK installed. Hadoop binaries are needed and the wintutils are needed in order to get Hadoop running as expected. 

Environment Variables:
The environment variables JAVA_HOME and HADOOP_HOME should be created in order to avoid any issues. Furthermore, PATH variables need to be edited to add the binaries for Java and Hadoop.

Configuring Hadoop Cluster:
%HADOOP_HOME%\etc\hadoop\hdfs-site.xml
%HADOOP_HOME%\etc\hadoop\core-site.xml
%HADOOP_HOME%\etc\hadoop\mapred-site.xml
%HADOOP_HOME%\etc\hadoop\yarn-site.xml

HDFS site config
Create directories for the master node(namenode) and then for the data store(datanode).
Eg. C:\hadoop-3.2.1\data\dfs\namenode & C:\hadoop-3.2.1\data\dfs\datanode

“hdfs-site.xml”
*Insert between the Configuration element in the xml file
<property>
<name>dfs.replication</name>
<value>1</value>
</property>
<property>
<name>dfs.namenode.name.dir</name>
<value>file:///C:/hadoop-3.2.1/data/dfs/namenode</value>
</property>
<property>
<name>dfs.datanode.data.dir</name>
<value>file:///C:/hadoop-3.2.1/data/dfs/datanode</value>
</property>
