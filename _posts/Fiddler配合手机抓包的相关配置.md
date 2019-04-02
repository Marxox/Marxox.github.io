---
title: Fiddler配合手机抓包的相关配置
date: 2019-01-28 10:12:30
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/86671787   
  Fiddler安装包地址：[https://pan.baidu.com/s/1qepvOoPo9pHWspW3HUBy_A](https://pan.baidu.com/s/1qepvOoPo9pHWspW3HUBy_A)

 下面是用笔记本（win10），手机（小米Note3）进行的相关配置。

 安装完Fiddler后，打开Fiddler：

 选择菜单栏Tools---Options...

 ![](https://img-blog.csdnimg.cn/20190128074856795.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 然后弹出以下窗口，按照下面这些图片进行配置（设置过程中会有弹框，都允许）：

 ![](https://img-blog.csdnimg.cn/2019012808012273.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 ![](https://img-blog.csdnimg.cn/20190128080137847.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 下图中的端口号（红色箭头所指位置，可以是“6666”，“8888”之类的，具体规则可以百度）

 ![](https://img-blog.csdnimg.cn/20190128080652342.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 配置完后，**重启Fiddler**。

 
--------
电脑先配置到这吧，接下来配置手机。

 手机连接电脑的热点，并在手机上设置连接的WLAN的代理，如下图所示：

 **代理：**手动

 **主机名：**电脑ip地址，例如：192.168.137.1

 下图中的“路由器”对应的地址就是主机名

 **端口：**Fiddler刚才设置的端口号，例如：9999

 **IP 设置：**DHCP

 ![](https://img-blog.csdnimg.cn/2019012808342748.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 电脑ip地址（主机名）查询办法：电脑打开cmd，输入“ipconfig”，然后回车，如下图所示：

 ![](https://img-blog.csdnimg.cn/20190128084553175.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 代理配置完后，手机打开浏览器，在地址栏输入“主机名+端口号”，例如：192.168.137.1：9999

 接着会出现如下界面，点击红色箭头所指的“FiddlerRoot certificate”，下载证书并安装：

 ![](https://img-blog.csdnimg.cn/20190128090503286.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 手机如何安装证书：设置---WLAN---高级设置---安装证书

 点击“安装证书”，在弹出的页面中找到刚才下载的证书并安装。

 
--------
按照上面设置后，如果手机连不上网，那么可以进行以下操作：

 电脑打开控制面板，弹出如下窗口：

 ![](https://img-blog.csdnimg.cn/20190128093544230.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 点击“系统和安全”，弹出如下窗口：

 ![](https://img-blog.csdnimg.cn/20190128093811901.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 点击“Windows Defender 防火墙”，弹出如下窗口：

 ![](https://img-blog.csdnimg.cn/20190128094119643.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 点击“高级设置”，弹出如下窗口：

 ![](https://img-blog.csdnimg.cn/20190128094737384.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 点击“入站规则”后，在右侧窗口列表中找到“Fiddler”。

 选择其中两个协议分别为“TCP”和“UDP”的都进行以下设置：

 ![](https://img-blog.csdnimg.cn/20190128095935360.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 ![](https://img-blog.csdnimg.cn/20190128100009591.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 可能还有其他两个我们没有设置过的“Fiddler”规则，选中并右击，选择“禁用规则”。

 最后剩下两个已启用的“Fiddler”规则，对应的协议分别是“TCP”和“UDP”，配置文件都指定“专用”和“公用”。

 因为我自己电脑开的热点属于“公用网络”，所以进行以上设置。

 
--------
如果只想抓手机包，那么可以取消勾选“Act as system proxy on startup”，按照以下设置：

 ![](https://img-blog.csdnimg.cn/20190129091710748.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 做完上面一步再继续下面的操作。

 ![](https://img-blog.csdnimg.cn/2019012909175538.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 点击“WinINET Options”，弹出以下窗口（电脑的控制面板中也可以找到这个Internet属性设置）：

 ![](https://img-blog.csdnimg.cn/20190129092144463.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 点击“局域网设置”后，弹出下面的窗口：

 ![](https://img-blog.csdnimg.cn/20190129092655199.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 实际操作时，步骤及显示不一定完全一致。

 做完以上操作，Fiddler就不会代理PC端了。

 
--------

### 2019.3.17更新

 若Fiddler代理电脑后，电脑不能正常上网，建议更改“Fiddler监听端口”进行尝试。

   
 