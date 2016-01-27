#Configuration
Use the following: 

conf/core-site.xml:
```
<configuration>
     <property>
         <name>fs.default.name</name>
         <value>hdfs://localhost:9000</value>
     </property>
</configuration>
```
conf/hdfs-site.xml:
```
<configuration>
     <property>
         <name>dfs.replication</name>
         <value>1</value>
     </property>
</configuration>
```
conf/mapred-site.xml:
```
<configuration>
     <property>
         <name>mapred.job.tracker</name>
         <value>localhost:9001</value>
     </property>
</configuration>
```

#找不到JAVA_HOME
[Hadoop] Error: JAVA_HOME is not set 

在hadoop-env.sh中增加：
```
export JAVA_HOME=/your/jdk/root/path
```

#不停要密码
```
$ ssh-keygen -t dsa -P '' -f ~/.ssh/id_dsa 
$ cat ~/.ssh/id_dsa.pub >> ~/.ssh/authorized_keys
```

#无法向HDFS 1.x 文件追加内容
在hdfs-site.xml中：
```
     <property>
         <name>dfs.permissions</name>
         <value>false</value>
     </property>
     <property>
         <name>dfs.support.broken.append</name>
         <value>true</value>
     </property>
```
