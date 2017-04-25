## Hadoop2.6.5 Configuration

1.hadoop-env.sh = JAVA_HOME
2.yarn-env.sh   = JAVA_HOME
3.slaves

4.hdfs-site.xml
<configuration>
      <property>
        <name>dfs.namenode.rpc-address</name>
        <value>qcloud-master:9000</value>
      </property>
      <property>
          <name>dfs.namenode.http-address</name>
          <value>qcloud-master:50070</value>
      </property>
      <property>
          <name>dfs.namenode.secondary.http-address</name>
          <value>qcloud-master:50090</value>
      </property>
      <property>
          <name>dfs.namenode.name.dir</name>
          <value>file:/usr/local/hadoop/dfs/name</value>
      </property>
      <property>
          <name>dfs.datanode.data.dir</name>
          <value>file:/usr/local/hadoop/dfs/data</value>
      </property>
      <property>
        <name>dfs.blocksize</name>
        <value>67108864</value>
      </property>
      <property>
          <name>dfs.replication</name>
          <value>1</value>
      </property>
      <property>
          <name>dfs.nameservices</name>
          <value>qcloud-master</value>
      </property>
      <property>
          <name>dfs.webhdfs.enabled</name>
          <value>true</value>
      </property>
      <property>
          <name>dfs.permissions</name>
          <value>false</value>
      </property>
</configuration>


5.core-site.xml
<configuration>
       <property>
            <name>fs.defaultFS</name>
            <value>hdfs://qcloud-master:9000</value>
       </property>
       <property>
            <name>io.file.buffer.size</name>
            <value>131072</value>
        </property>
       <property>
            <name>hadoop.tmp.dir</name>
            <value>file:/usr/local/hadoop/tmp</value>
       </property>
</configuration>

6.mapred-site.xml
<configuration>
      <property>                                                                  
　　　　　　  <name>mapreduce.framework.name</name>
            <value>yarn</value>
      </property>
      <property>
            <name>mapreduce.jobhistory.address</name>
            <value>qcloud-master:10020</value>
      </property>
      <property>
            <name>mapreduce.jobhistory.webapp.address</name>
            <value>qcloud-master:19888</value>
       </property>
</configuration>

7.yarn-site.xml
<configuration>
      <property>
          <name>yarn.nodemanager.aux-services</name>
          <value>mapreduce_shuffle</value>
      </property>
      <property>
          <name>yarn.resourcemanager.hostname</name>
          <value>qcloud-master</value>
      </property>
</configuration>