---
title: 查询c1课程成绩大于c2课程成绩的学生学号（Oracle自连接）
date: 2018-12-22 22:31:40
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/85218804   
  表sc

 ![](https://img-blog.csdnimg.cn/20181222222622873.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 
```
 SELECT sc1.sno
FROM sc sc1,sc sc2
WHERE sc1.sno = sc2.sno AND 
      sc1.cno = 'c1' AND 
      sc2.cno = 'c2' AND 
      sc1.score > sc2.score;
```
 

   
 