#排除不要的class
##排除旧的
libraryDependencies += 
  "log4j" % "log4j" % "1.2.15" exclude("javax.jms", "jms")
##添加新的
拷到lib目录下。
