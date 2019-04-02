---
title: NVIDIA GeForce Experience报错
date: 2019-03-29 20:06:03
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/88900616   
  ![](https://img-blog.csdnimg.cn/20190329194929419.jpg)

 打开NVIDIA GeForce Experience出现以上错误或其他类似错误。很可能是“NVIDIA Telemetry Container”服务没有启动。

 
### **解决方法：**

 同时按“Windows键” + “R键”，在弹出的“运行”窗口中输入“services.msc”并“确定”。接着，在打开的“服务”窗口中找到“NVIDIA Telemetry Container”，将其“启动类型”设为“自动”并启动此服务。

 **注：1.**若启动“NVIDIA Telemetry Container”服务报错，那么鼠标右击此服务，选择“属性”，在其属性窗口中选择登录身份为“本地系统账户”并“确定”，然后启动此服务。

 ![](https://img-blog.csdnimg.cn/20190329205014881.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 ** 2.**若卡在登录界面进不进去，可尝试启动“NVIDIA NetworkService Container”服务。具体设置参考上文。

   
 