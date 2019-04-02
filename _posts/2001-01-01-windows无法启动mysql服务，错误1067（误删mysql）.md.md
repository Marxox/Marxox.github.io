---
title: windows无法启动mysql服务，错误1067（误删mysql）
date: 2019-03-19 14:49:16
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/88661917   
  我误删了“mysql”数据库（mysql自带的数据库）。然后，MySQL服务都启动不了，报错“1067”。

 **解决方法：**将“C:\Program Files (x86)\MySQL\MySQL Server 5.5\data”路径下的“mysql”文件夹拷贝到“C:\ProgramData\MySQL\MySQL Server 5.5\data”路径下。

 这一步没有问题的话，那么MySQL服务可以启动了。

 接下来，如果登录数据库时出现“SQL执行错误 # 1045.从数据库的响应：Access denied for user 'root'@'localhost'(using password: YES) 请检查用户名和口令.”，参考这篇文章：[https://blog.csdn.net/lzf_hlh/article/details/80885139](https://blog.csdn.net/lzf_hlh/article/details/80885139)

   
 