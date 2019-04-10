---
title: NVIDIA GeForce Experience报错
date: 2019-03-29 20:06:03
categories:
- 各种问题
---

![]({{site.url}}/assets/img/20190329194647_看图王.jpg)

打开NVIDIA GeForce Experience出现以上错误或其他类似错误。很可能是“NVIDIA Telemetry Container”服务没有启动。

### 解决方法：

同时按“Windows键” + “R键”，在弹出的“运行”窗口中输入“services.msc”并“确定”。接着，在打开的“服务”窗口中找到“NVIDIA Telemetry Container”，将其“启动类型”设为“自动”并启动此服务。

**注：1.**若启动“NVIDIA Telemetry Container”服务报错，那么鼠标右击此服务，选择“属性”，在其属性窗口中选择登录身份为“本地系统账户”并“确定”，然后启动此服务：

![]({{site.url}}/assets/img/20190329204501.jpg)

​	**2.**若卡在登录界面进不进去，可尝试启动“NVIDIA NetworkService Container”服务。具体设置参考上文。   



***

### 2019.4.2更新

软件和系统的兼容性也可能导致报错。可进行以下尝试：

右击“GeForce Experience”的启动图标，选择“属性”。在“GeForce Experience 属性”窗口中，切换到“兼容性”那栏，选择各种系统，尝试“以兼容模式运行这个程序”：

![]({{site.url}}/assets/img/20190402131052.jpg)











