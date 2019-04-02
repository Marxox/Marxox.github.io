---
title: Java连接oracle数据库报错（JDBC）
date: 2018-12-18 13:05:48
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/85063272   
  首先定位到准确的代码报错位置。如果是在下面的代码处报错

 
```
 conn = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:XE", "scott", "tiger");
```
 那可能是ojdbc.jar版本问题，可以换其他版本尝试。

 下面是ojdbc6和ojdbc7-12.1.0.2的地址，需要的自取。

 链接: [https://pan.baidu.com/s/1-Ale1TpFa5DQbTFdQj2o3w](https://pan.baidu.com/s/1-Ale1TpFa5DQbTFdQj2o3w)

 提取码: cepu 

 

 下面是测试

 环境配置：

 java version "1.7.0_17"

 Oracle Database 11g

 

 错误提示信息一（用的ojdbc14.jar）：

 提示空指针异常

 
```
 Exception in thread "main" java.lang.NullPointerException
	at java.lang.String.<init>(Unknown Source)
	at oracle.sql.CharacterSet.AL32UTF8ToString(CharacterSet.java:1517)
	at oracle.jdbc.driver.DBConversion.CharBytesToString(DBConversion.java:589)
	at oracle.jdbc.driver.DBConversion.CharBytesToString(DBConversion.java:542)
	at oracle.jdbc.driver.T4CTTIoauthenticate.receiveOauth(T4CTTIoauthenticate.java:822)
	at oracle.jdbc.driver.T4CConnection.logon(T4CConnection.java:362)
	at oracle.jdbc.driver.PhysicalConnection.<init>(PhysicalConnection.java:439)
	at oracle.jdbc.driver.T4CConnection.<init>(T4CConnection.java:165)
	at oracle.jdbc.driver.T4CDriverExtension.getConnection(T4CDriverExtension.java:35)
	at oracle.jdbc.driver.OracleDriver.connect(OracleDriver.java:801)
	at java.sql.DriverManager.getConnection(Unknown Source)
	at java.sql.DriverManager.getConnection(Unknown Source)
	at com.jdbc.JdbcEmp.main(JdbcEmp.java:21)
```
 

 错误提示信息二（用的ojdbc6.jar）：

 
```
 java.sql.SQLRecoverableException: Io 异常: Undefined Error
	at oracle.jdbc.driver.SQLStateMapping.newSQLException(SQLStateMapping.java:101)
	at oracle.jdbc.driver.DatabaseError.newSQLException(DatabaseError.java:112)
	at oracle.jdbc.driver.DatabaseError.throwSqlException(DatabaseError.java:173)
	at oracle.jdbc.driver.DatabaseError.throwSqlException(DatabaseError.java:229)
	at oracle.jdbc.driver.DatabaseError.throwSqlException(DatabaseError.java:458)
	at oracle.jdbc.driver.T4CConnection.logon(T4CConnection.java:411)
	at oracle.jdbc.driver.PhysicalConnection.<init>(PhysicalConnection.java:490)
	at oracle.jdbc.driver.T4CConnection.<init>(T4CConnection.java:202)
	at oracle.jdbc.driver.T4CDriverExtension.getConnection(T4CDriverExtension.java:33)
	at oracle.jdbc.driver.OracleDriver.connect(OracleDriver.java:474)
	at java.sql.DriverManager.getConnection(Unknown Source)
	at java.sql.DriverManager.getConnection(Unknown Source)
	at com.jdbc.JdbcEmp.main(JdbcEmp.java:21)



```
 也许某些问题和保存路径存在中文有关。

   
 