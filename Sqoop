#使用

1.MYSQL数据导入HDFS（导入default dir（/usr/<username>））

语法：sqoop import --conect <数据库连接字符串> --usernamem --<username> --password -<password> --table <表明>  --fields-terminated-by '<column之间的分隔符>'  --null string '<is null 用**(--可能会出现特殊字符问题)>' -m <map任务数量> --append(追加内容) --hive-import （向hive中添加） 

sqoop  import --connect jdbc:mysql://zouyan0:3306/hive --username -root --passord -admin --table <表名> --fields-terminated-by '\t'  --null-string '**'  -m 1 --append  --hive-import

2.向HDFS中导入增量

语法：--check-column ‘<增量标志>' --incremental <增量方式,如appent，追加的方式导入>--last-value <之前最大值>

  sqoop import --connect jdbc:mysql://zouyan0:3306/hive  --username root --password admin --table TBLS --fields-terminated-by '\t'  --null-string '**'  -m 1 --append  --hive-import  --check-column 'TBL_ID' --incremental append --last-value 6

3.把数据从hdfs导出到mysql中  
  sqoop export --connect jdbc:mysql://zouyan0:3306/hive  --username root --password admin --table ids --fields-terminated-by '\t' --export-dir '/ids'

4.设置为作业，运行作业(直接运行方便)
  sqoop job --create myjob -- import --connect jdbc:mysql://hadoop0:3306/hive  --username root --password admin --table TBLS --fields-terminated-by '\t'  --null-string '**'  -m 1 --append  --hive-import 

5.删除作业
  sqoop job --delete myjob 
6.设置为作业，运行作业
 sqoop job --exec myjob

7. 导入导出的事务是以Mapper任务为单位,控制事物，需要控制Map
