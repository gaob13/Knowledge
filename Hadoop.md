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
