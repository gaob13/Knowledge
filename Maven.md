#mvn:install故障
##Wrap失败
```
[ERROR] Failed to execute goal net.alchim31.maven:scala-maven-plugin:3.2.2:doc-jar (attach-scaladocs) on project spark-streaming-kafka_2.10: MavenReportException: Error while creating archive: wrap: Process exited with an error: 1 (Exit value: 1) -> [Help 1]
```
原因是正在使用要安装的jar包。应该先停掉相应程序。
##代码风格检查不过
```
[INFO] --- scalastyle-maven-plugin:0.7.0:check (default) @ spark-streaming-kafka_2.10 ---
error file=/home/gaobin/git-hub/spark/external/kafka/src/main/scala/org/apache/spark/streaming/kafka/DirectKafkaInputDStream.scala message=File line length exceeds 100 characters line=67
Saving to outputFile=/home/gaobin/git-hub/spark/external/kafka/target/scalastyle-output.xml
Processed 11 file(s)

...

[ERROR] Failed to execute goal org.scalastyle:scalastyle-maven-plugin:0.7.0:check (default) on project spark-streaming-kafka_2.10: Failed during scalastyle execution: You have 1 Scalastyle violation(s). -> [Help 1]
```
原因是一行代码太长了。晕。
