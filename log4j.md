#Maven
##slf4j-log4j12
```xml
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-log4j12</artifactId>
			<version>1.6.1</version>
		</dependency>
```
#log4j.properties
```properties
#config root logger
log4j.rootLogger = INFO,system.out
log4j.appender.system.out=org.apache.log4j.ConsoleAppender
log4j.appender.system.out.layout=org.apache.log4j.PatternLayout
log4j.appender.system.out.layout.ConversionPattern=MINAServer Logger-->%5p{%F:%L}-%m%n

#config this Project.file logger
log4j.logger.thisProject.file=INFO,thisProject.file.out
log4j.appender.thisProject.file.out=org.apache.log4j.DailyRollingFileAppender
log4j.appender.thisProject.file.out.File=logContentFile.log
log4j.appender.thisProject.file.out.layout=org.apache.log4j.PatternLayout
```

#log4j不打log
##找不到Appender
```
log4j:WARN No appenders could be found for logger (org.apache.flume.lifecycle.LifecycleSupervisor).
log4j:WARN Please initialize the log4j system properly.
log4j:WARN See http://logging.apache.org/log4j/1.2/faq.html#noconfig for more info.
```
加入参数
```
-Dflume.root.logger=INFO,console
-Dlog4j.configuration=file:/home/gaobin/tlhz-flume/apache-flume-1.6.0-bin/conf/log4j.properties
```
