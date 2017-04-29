## Spark 1.6.2 Configuration

1.spark-env.sh

```
配置项
说明

SPARK_LOCAL_IP= 10.47.110.38 本机ip或hostname（不同主机配置不同）
SPARK_LOCAL_DIRS=/data/spark/local 配置spark的local目录
SPARK_MASTER_IP= 10.47.110.38 master节点ip或hostname
SPARK_MASTER_WEBUI_PORT=8080 web页面端口
SPARK_WORKER_CORES=2 Worker的cpu核数
SPARK_WORKER_MEMORY=8g worker内存大小
SPARK_WORKER_DIR=/data/spark/work worker目录
export SPARK_MASTER_OPTS="-Dspark.deploy.defaultCores=4" spark-shell启动使用核数

export SPARK_WORKER_OPTS="-Dspark.worker.cleanup.enabled=true -Dspark.worker.cleanup.appDataTtl=604800"

worker自动清理及清理时间间隔
 
 
export SPARK_HISTORY_OPTS="-Dspark.history.ui.port=18080 -Dspark.history.retainedApplications=3 -Dspark.history.fs.logDirectory=hdfs://systex/user/spark/applicationHistory"

history server页面端口、备份数、log日志在HDFS的位置（注意，需要在HDFS上新建对应的路径）

SPARK_LOG_DIR=/data/spark/log 配置Spark的log日志目录 
export JAVA_HOME=/usr/local/jdk/ 配置java路径
export SCALA_HOME=/usr/local/scala/ 配置scala路径
export HADOOP_HOME=/opt/cloudera/parcels/CDH/lib/hadoop 配置hadoop的lib路径
export HADOOP_CONF_DIR=/etc/hadoop/conf 配置hadoop的配置路径
```

2.slaves

qcloud-slave1
qcloud-slave2