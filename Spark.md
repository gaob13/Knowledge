#连不上HDFS
拒绝连接
```
16/01/26 20:07:50 ERROR Executor: Exception in task 0.0 in stage 1.0 (TID 2)
java.io.IOException: Failed on local exception: java.io.EOFException; Host Details : local host is: "gaobin-beaver/127.0.0.1"; destination host is: "192.168.1.100":9000; 
	at org.apache.hadoop.net.NetUtils.wrapException(NetUtils.java:764)
	at org.apache.hadoop.ipc.Client.call(Client.java:1351)
	at org.apache.hadoop.ipc.Client.call(Client.java:1300)
	at org.apache.hadoop.ipc.ProtobufRpcEngine$Invoker.invoke(ProtobufRpcEngine.java:206)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:606)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invokeMethod(RetryInvocationHandler.java:186)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invoke(RetryInvocationHandler.java:102)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at org.apache.hadoop.hdfs.protocolPB.ClientNamenodeProtocolTranslatorPB.getFileInfo(ClientNamenodeProtocolTranslatorPB.java:651)
	at org.apache.hadoop.hdfs.DFSClient.getFileInfo(DFSClient.java:1679)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1106)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystemLinkResolver.resolve(FileSystemLinkResolver.java:81)
	at org.apache.hadoop.hdfs.DistributedFileSystem.getFileStatus(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystem.exists(FileSystem.java:1397)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:64)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:49)
	at scala.collection.Iterator$class.foreach(Iterator.scala:727)
	at org.apache.spark.util.collection.AppendOnlyMap$$anon$1.foreach(AppendOnlyMap.scala:165)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:49)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:66)
	at org.apache.spark.scheduler.Task.run(Task.scala:88)
	at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:214)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
	at java.lang.Thread.run(Thread.java:745)
Caused by: java.io.EOFException
	at java.io.DataInputStream.readInt(DataInputStream.java:392)
	at org.apache.hadoop.ipc.Client$Connection.receiveRpcResponse(Client.java:995)
	at org.apache.hadoop.ipc.Client$Connection.run(Client.java:891)
16/01/26 20:07:50 WARN TaskSetManager: Lost task 0.0 in stage 1.0 (TID 2, localhost): java.io.IOException: Failed on local exception: java.io.EOFException; Host Details : local host is: "gaobin-beaver/127.0.0.1"; destination host is: "192.168.1.100":9000; 
	at org.apache.hadoop.net.NetUtils.wrapException(NetUtils.java:764)
	at org.apache.hadoop.ipc.Client.call(Client.java:1351)
	at org.apache.hadoop.ipc.Client.call(Client.java:1300)
	at org.apache.hadoop.ipc.ProtobufRpcEngine$Invoker.invoke(ProtobufRpcEngine.java:206)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:606)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invokeMethod(RetryInvocationHandler.java:186)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invoke(RetryInvocationHandler.java:102)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at org.apache.hadoop.hdfs.protocolPB.ClientNamenodeProtocolTranslatorPB.getFileInfo(ClientNamenodeProtocolTranslatorPB.java:651)
	at org.apache.hadoop.hdfs.DFSClient.getFileInfo(DFSClient.java:1679)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1106)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystemLinkResolver.resolve(FileSystemLinkResolver.java:81)
	at org.apache.hadoop.hdfs.DistributedFileSystem.getFileStatus(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystem.exists(FileSystem.java:1397)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:64)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:49)
	at scala.collection.Iterator$class.foreach(Iterator.scala:727)
	at org.apache.spark.util.collection.AppendOnlyMap$$anon$1.foreach(AppendOnlyMap.scala:165)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:49)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:66)
	at org.apache.spark.scheduler.Task.run(Task.scala:88)
	at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:214)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
	at java.lang.Thread.run(Thread.java:745)
Caused by: java.io.EOFException
	at java.io.DataInputStream.readInt(DataInputStream.java:392)
	at org.apache.hadoop.ipc.Client$Connection.receiveRpcResponse(Client.java:995)
	at org.apache.hadoop.ipc.Client$Connection.run(Client.java:891)

16/01/26 20:07:50 ERROR TaskSetManager: Task 0 in stage 1.0 failed 1 times; aborting job
16/01/26 20:07:50 ERROR JobScheduler: Error running job streaming job 1453810070000 ms.0
org.apache.spark.SparkException: Job aborted due to stage failure: Task 0 in stage 1.0 failed 1 times, most recent failure: Lost task 0.0 in stage 1.0 (TID 2, localhost): java.io.IOException: Failed on local exception: java.io.EOFException; Host Details : local host is: "gaobin-beaver/127.0.0.1"; destination host is: "192.168.1.100":9000; 
	at org.apache.hadoop.net.NetUtils.wrapException(NetUtils.java:764)
	at org.apache.hadoop.ipc.Client.call(Client.java:1351)
	at org.apache.hadoop.ipc.Client.call(Client.java:1300)
	at org.apache.hadoop.ipc.ProtobufRpcEngine$Invoker.invoke(ProtobufRpcEngine.java:206)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:606)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invokeMethod(RetryInvocationHandler.java:186)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invoke(RetryInvocationHandler.java:102)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at org.apache.hadoop.hdfs.protocolPB.ClientNamenodeProtocolTranslatorPB.getFileInfo(ClientNamenodeProtocolTranslatorPB.java:651)
	at org.apache.hadoop.hdfs.DFSClient.getFileInfo(DFSClient.java:1679)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1106)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystemLinkResolver.resolve(FileSystemLinkResolver.java:81)
	at org.apache.hadoop.hdfs.DistributedFileSystem.getFileStatus(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystem.exists(FileSystem.java:1397)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:64)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:49)
	at scala.collection.Iterator$class.foreach(Iterator.scala:727)
	at org.apache.spark.util.collection.AppendOnlyMap$$anon$1.foreach(AppendOnlyMap.scala:165)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:49)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:66)
	at org.apache.spark.scheduler.Task.run(Task.scala:88)
	at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:214)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
	at java.lang.Thread.run(Thread.java:745)
Caused by: java.io.EOFException
	at java.io.DataInputStream.readInt(DataInputStream.java:392)
	at org.apache.hadoop.ipc.Client$Connection.receiveRpcResponse(Client.java:995)
	at org.apache.hadoop.ipc.Client$Connection.run(Client.java:891)

Driver stacktrace:
	at org.apache.spark.scheduler.DAGScheduler.org$apache$spark$scheduler$DAGScheduler$$failJobAndIndependentStages(DAGScheduler.scala:1283)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$abortStage$1.apply(DAGScheduler.scala:1271)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$abortStage$1.apply(DAGScheduler.scala:1270)
	at scala.collection.mutable.ResizableArray$class.foreach(ResizableArray.scala:59)
	at scala.collection.mutable.ArrayBuffer.foreach(ArrayBuffer.scala:47)
	at org.apache.spark.scheduler.DAGScheduler.abortStage(DAGScheduler.scala:1270)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$handleTaskSetFailed$1.apply(DAGScheduler.scala:697)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$handleTaskSetFailed$1.apply(DAGScheduler.scala:697)
	at scala.Option.foreach(Option.scala:236)
	at org.apache.spark.scheduler.DAGScheduler.handleTaskSetFailed(DAGScheduler.scala:697)
	at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.doOnReceive(DAGScheduler.scala:1496)
	at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:1458)
	at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:1447)
	at org.apache.spark.util.EventLoop$$anon$1.run(EventLoop.scala:48)
	at org.apache.spark.scheduler.DAGScheduler.runJob(DAGScheduler.scala:567)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1822)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1835)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1848)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1919)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1.apply(RDD.scala:896)
	at org.apache.spark.rdd.RDDOperationScope$.withScope(RDDOperationScope.scala:147)
	at org.apache.spark.rdd.RDDOperationScope$.withScope(RDDOperationScope.scala:108)
	at org.apache.spark.rdd.RDD.withScope(RDD.scala:306)
	at org.apache.spark.rdd.RDD.foreachPartition(RDD.scala:896)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1.apply(KafkaDStreamFunctions.scala:46)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1$$anonfun$apply$mcV$sp$1.apply$mcV$sp(ForEachDStream.scala:42)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1$$anonfun$apply$mcV$sp$1.apply(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1$$anonfun$apply$mcV$sp$1.apply(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.DStream.createRDDWithLocalProperties(DStream.scala:399)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1.apply$mcV$sp(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1.apply(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1.apply(ForEachDStream.scala:40)
	at scala.util.Try$.apply(Try.scala:161)
	at org.apache.spark.streaming.scheduler.Job.run(Job.scala:34)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler$$anonfun$run$1.apply$mcV$sp(JobScheduler.scala:218)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler$$anonfun$run$1.apply(JobScheduler.scala:218)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler$$anonfun$run$1.apply(JobScheduler.scala:218)
	at scala.util.DynamicVariable.withValue(DynamicVariable.scala:57)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler.run(JobScheduler.scala:217)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
	at java.lang.Thread.run(Thread.java:745)
Caused by: java.io.IOException: Failed on local exception: java.io.EOFException; Host Details : local host is: "gaobin-beaver/127.0.0.1"; destination host is: "192.168.1.100":9000; 
	at org.apache.hadoop.net.NetUtils.wrapException(NetUtils.java:764)
	at org.apache.hadoop.ipc.Client.call(Client.java:1351)
	at org.apache.hadoop.ipc.Client.call(Client.java:1300)
	at org.apache.hadoop.ipc.ProtobufRpcEngine$Invoker.invoke(ProtobufRpcEngine.java:206)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:606)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invokeMethod(RetryInvocationHandler.java:186)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invoke(RetryInvocationHandler.java:102)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at org.apache.hadoop.hdfs.protocolPB.ClientNamenodeProtocolTranslatorPB.getFileInfo(ClientNamenodeProtocolTranslatorPB.java:651)
	at org.apache.hadoop.hdfs.DFSClient.getFileInfo(DFSClient.java:1679)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1106)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystemLinkResolver.resolve(FileSystemLinkResolver.java:81)
	at org.apache.hadoop.hdfs.DistributedFileSystem.getFileStatus(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystem.exists(FileSystem.java:1397)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:64)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:49)
	at scala.collection.Iterator$class.foreach(Iterator.scala:727)
	at org.apache.spark.util.collection.AppendOnlyMap$$anon$1.foreach(AppendOnlyMap.scala:165)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:49)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:66)
	at org.apache.spark.scheduler.Task.run(Task.scala:88)
	at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:214)
	... 3 more
Caused by: java.io.EOFException
	at java.io.DataInputStream.readInt(DataInputStream.java:392)
	at org.apache.hadoop.ipc.Client$Connection.receiveRpcResponse(Client.java:995)
	at org.apache.hadoop.ipc.Client$Connection.run(Client.java:891)
Exception in thread "main" org.apache.spark.SparkException: Job aborted due to stage failure: Task 0 in stage 1.0 failed 1 times, most recent failure: Lost task 0.0 in stage 1.0 (TID 2, localhost): java.io.IOException: Failed on local exception: java.io.EOFException; Host Details : local host is: "gaobin-beaver/127.0.0.1"; destination host is: "192.168.1.100":9000; 
	at org.apache.hadoop.net.NetUtils.wrapException(NetUtils.java:764)
	at org.apache.hadoop.ipc.Client.call(Client.java:1351)
	at org.apache.hadoop.ipc.Client.call(Client.java:1300)
	at org.apache.hadoop.ipc.ProtobufRpcEngine$Invoker.invoke(ProtobufRpcEngine.java:206)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:606)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invokeMethod(RetryInvocationHandler.java:186)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invoke(RetryInvocationHandler.java:102)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at org.apache.hadoop.hdfs.protocolPB.ClientNamenodeProtocolTranslatorPB.getFileInfo(ClientNamenodeProtocolTranslatorPB.java:651)
	at org.apache.hadoop.hdfs.DFSClient.getFileInfo(DFSClient.java:1679)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1106)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystemLinkResolver.resolve(FileSystemLinkResolver.java:81)
	at org.apache.hadoop.hdfs.DistributedFileSystem.getFileStatus(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystem.exists(FileSystem.java:1397)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:64)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:49)
	at scala.collection.Iterator$class.foreach(Iterator.scala:727)
	at org.apache.spark.util.collection.AppendOnlyMap$$anon$1.foreach(AppendOnlyMap.scala:165)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:49)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:66)
	at org.apache.spark.scheduler.Task.run(Task.scala:88)
	at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:214)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
	at java.lang.Thread.run(Thread.java:745)
Caused by: java.io.EOFException
	at java.io.DataInputStream.readInt(DataInputStream.java:392)
	at org.apache.hadoop.ipc.Client$Connection.receiveRpcResponse(Client.java:995)
	at org.apache.hadoop.ipc.Client$Connection.run(Client.java:891)

Driver stacktrace:
	at org.apache.spark.scheduler.DAGScheduler.org$apache$spark$scheduler$DAGScheduler$$failJobAndIndependentStages(DAGScheduler.scala:1283)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$abortStage$1.apply(DAGScheduler.scala:1271)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$abortStage$1.apply(DAGScheduler.scala:1270)
	at scala.collection.mutable.ResizableArray$class.foreach(ResizableArray.scala:59)
	at scala.collection.mutable.ArrayBuffer.foreach(ArrayBuffer.scala:47)
	at org.apache.spark.scheduler.DAGScheduler.abortStage(DAGScheduler.scala:1270)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$handleTaskSetFailed$1.apply(DAGScheduler.scala:697)
	at org.apache.spark.scheduler.DAGScheduler$$anonfun$handleTaskSetFailed$1.apply(DAGScheduler.scala:697)
	at scala.Option.foreach(Option.scala:236)
	at org.apache.spark.scheduler.DAGScheduler.handleTaskSetFailed(DAGScheduler.scala:697)
	at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.doOnReceive(DAGScheduler.scala:1496)
	at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:1458)
	at org.apache.spark.scheduler.DAGSchedulerEventProcessLoop.onReceive(DAGScheduler.scala:1447)
	at org.apache.spark.util.EventLoop$$anon$1.run(EventLoop.scala:48)
	at org.apache.spark.scheduler.DAGScheduler.runJob(DAGScheduler.scala:567)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1822)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1835)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1848)
	at org.apache.spark.SparkContext.runJob(SparkContext.scala:1919)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1.apply(RDD.scala:896)
	at org.apache.spark.rdd.RDDOperationScope$.withScope(RDDOperationScope.scala:147)
	at org.apache.spark.rdd.RDDOperationScope$.withScope(RDDOperationScope.scala:108)
	at org.apache.spark.rdd.RDD.withScope(RDD.scala:306)
	at org.apache.spark.rdd.RDD.foreachPartition(RDD.scala:896)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1.apply(KafkaDStreamFunctions.scala:46)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1$$anonfun$apply$mcV$sp$1.apply$mcV$sp(ForEachDStream.scala:42)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1$$anonfun$apply$mcV$sp$1.apply(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1$$anonfun$apply$mcV$sp$1.apply(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.DStream.createRDDWithLocalProperties(DStream.scala:399)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1.apply$mcV$sp(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1.apply(ForEachDStream.scala:40)
	at org.apache.spark.streaming.dstream.ForEachDStream$$anonfun$1.apply(ForEachDStream.scala:40)
	at scala.util.Try$.apply(Try.scala:161)
	at org.apache.spark.streaming.scheduler.Job.run(Job.scala:34)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler$$anonfun$run$1.apply$mcV$sp(JobScheduler.scala:218)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler$$anonfun$run$1.apply(JobScheduler.scala:218)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler$$anonfun$run$1.apply(JobScheduler.scala:218)
	at scala.util.DynamicVariable.withValue(DynamicVariable.scala:57)
	at org.apache.spark.streaming.scheduler.JobScheduler$JobHandler.run(JobScheduler.scala:217)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
	at java.lang.Thread.run(Thread.java:745)
Caused by: java.io.IOException: Failed on local exception: java.io.EOFException; Host Details : local host is: "gaobin-beaver/127.0.0.1"; destination host is: "192.168.1.100":9000; 
	at org.apache.hadoop.net.NetUtils.wrapException(NetUtils.java:764)
	at org.apache.hadoop.ipc.Client.call(Client.java:1351)
	at org.apache.hadoop.ipc.Client.call(Client.java:1300)
	at org.apache.hadoop.ipc.ProtobufRpcEngine$Invoker.invoke(ProtobufRpcEngine.java:206)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:606)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invokeMethod(RetryInvocationHandler.java:186)
	at org.apache.hadoop.io.retry.RetryInvocationHandler.invoke(RetryInvocationHandler.java:102)
	at com.sun.proxy.$Proxy17.getFileInfo(Unknown Source)
	at org.apache.hadoop.hdfs.protocolPB.ClientNamenodeProtocolTranslatorPB.getFileInfo(ClientNamenodeProtocolTranslatorPB.java:651)
	at org.apache.hadoop.hdfs.DFSClient.getFileInfo(DFSClient.java:1679)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1106)
	at org.apache.hadoop.hdfs.DistributedFileSystem$17.doCall(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystemLinkResolver.resolve(FileSystemLinkResolver.java:81)
	at org.apache.hadoop.hdfs.DistributedFileSystem.getFileStatus(DistributedFileSystem.java:1102)
	at org.apache.hadoop.fs.FileSystem.exists(FileSystem.java:1397)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:64)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1$$anonfun$apply$2.apply(KafkaDStreamFunctions.scala:49)
	at scala.collection.Iterator$class.foreach(Iterator.scala:727)
	at org.apache.spark.util.collection.AppendOnlyMap$$anon$1.foreach(AppendOnlyMap.scala:165)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:49)
	at org.apache.spark.streaming.dstream.KafkaDStreamFunctions$$anonfun$saveAsKVFiles$1$$anonfun$1$$anonfun$apply$1.apply(KafkaDStreamFunctions.scala:48)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.rdd.RDD$$anonfun$foreachPartition$1$$anonfun$apply$29.apply(RDD.scala:898)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.SparkContext$$anonfun$runJob$5.apply(SparkContext.scala:1848)
	at org.apache.spark.scheduler.ResultTask.runTask(ResultTask.scala:66)
	at org.apache.spark.scheduler.Task.run(Task.scala:88)
	at org.apache.spark.executor.Executor$TaskRunner.run(Executor.scala:214)
	... 3 more
Caused by: java.io.EOFException
	at java.io.DataInputStream.readInt(DataInputStream.java:392)
	at org.apache.hadoop.ipc.Client$Connection.receiveRpcResponse(Client.java:995)
	at org.apache.hadoop.ipc.Client$Connection.run(Client.java:891)
```
hdfs-client 版本问题
```
可能是SBT把正确版本evict掉了。
```
