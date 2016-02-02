#mvn:install故障
##Wrap失败
```
[ERROR] Failed to execute goal net.alchim31.maven:scala-maven-plugin:3.2.2:doc-jar (attach-scaladocs) on project spark-streaming-kafka_2.10: MavenReportException: Error while creating archive: wrap: Process exited with an error: 1 (Exit value: 1) -> [Help 1]
```
原因是正在使用要安装的jar包。应该先停掉相应程序。
