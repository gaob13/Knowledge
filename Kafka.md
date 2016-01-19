#无限重启故障
发现如下故障

  java.lang.IllegalArgumentException: requirement failed: Corrupt index found, index file (/home/hadoop/kafka_2.10-0.8.2.1/var/log/kafka/test4-1/00000000000000000000.index) has non-zero size but the last offset is 0 and the base offset is 0

解决：

  删掉了log下面的所有topic目录
  
#外网不能访问
从内网三台机器可以互相访问，但是外网无法与broker建立连接
TODO:正待解决！
