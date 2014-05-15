# Cluster architecture

This is a single-node CDH4 cluster with the following services:

* Node `cloudera0`
  * HDFS: 
    * namenode
    * datanode
  * Map/Reduce v1
    * jobtracker
    * tasktracker

All nodes have a `vagrant` user (password: `vagrant`).

# Installation

navigate to the project root directory and run:

    vagrant up

## Update your /etc/hosts file

Add the following line:

    192.168.56.20   localHdfsCluster

# Webapps

* HDFS namenode: http://192.168.56.20:50070/
* Map/Reduce jobtracker:  http://192.168.56.20:50030/

# Considerations

## HDFS permissions (no more required)

If you need to disable user permissions in HDFS add the following parameter to `/etc/hadoop/conf/hdfs-site.xml` (restarting services is required):

```
  <property>
    <name>dfs.permissions</name>
    <value>false</value>
  </property>
```

# Old Installation Procedure

```
git clone https://github.com/nguyenvanthan/vagrant-cdh4-pseudo-mrv1
cd vagrant-cdh4-pseudo-mrv1
vagrant up
```