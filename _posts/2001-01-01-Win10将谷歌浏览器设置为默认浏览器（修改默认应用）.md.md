---
title: Win10将谷歌浏览器设置为默认浏览器（修改默认应用）
date: 2019-01-07 21:18:18
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/86027896   
  不管是设置默认浏览器还是其他默认应用，建议看完整篇文章及链接。

 
--------
下面是几个月前遇到此问题时，我尝试的办法：

 安装完谷歌浏览器，想将它设置为默认浏览器，但系统的默认应用设置里一直不显示“谷歌浏览器”这一项。如下图所示：

 ![](https://img-blog.csdnimg.cn/20190107211629356.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

 解决办法：重新启动电脑，然后打开谷歌浏览器，谷歌浏览器主页面会提示它不是默认浏览器，选择“”设为默认浏览器“”。

 接下来到系统所有设置——应用——默认应用——Web浏览器（上图所示位置）中，选择“Google Chrome”。

 注：如果选择“Googe Chrome”后默认浏览器没有变为谷歌浏览器，就点击下图中的“重置”按钮，然后选择“Google Chrome”为默认浏览器。

 ![](https://img-blog.csdnimg.cn/20190109160348336.jpg)

 
--------

### **2019.3.9更新**

 我用上面的方法，只是临时有效，重启电脑后默认浏览器又变成了QQ浏览器。我当时以为问题是腾讯电脑管家锁定默认浏览器导致的。后来我将腾讯电脑管家卸载了，但是没什么改善，也许是腾讯电脑管家遗留在注册表中的痕迹没有清理干净（我不懂注册表，只有个大概的认识）。经过一些尝试后，我发现这和win10自带的Windows Defender有关。不过，我没找到具体是哪一个设置。我将Windows Defender关闭了。修改默认浏览器成功后，重启电脑后依然有效。

 **如何关闭Windows Defender，可以参考[https://blog.csdn.net/lsx2017/article/details/81386125](https://blog.csdn.net/lsx2017/article/details/81386125)**

 同时，如果遇到一些其他有关Windows Defender防火墙的问题，例如：局域网中，拷贝其他电脑共享的文件报错。关闭Windows Defender防火墙也可以解决。

 我觉得关闭Windows Defender防火墙会存在安全隐患，尽管我日常使用电脑还没遇到。这还需要自己多加注意。

 我电脑系统为Windows 10 Version 1803，换成其他版本，或者win7系统也许能解决问题，不过太麻烦了，不建议。

 
--------
我在网上还找到了其他的办法，有兴趣的可以尝试下：

 [https://www.jianshu.com/p/7b5a7b304c2c?from=timeline&isappinstalled=0](https://www.jianshu.com/p/7b5a7b304c2c?from=timeline&amp;isappinstalled=0)

 [https://stackoverflow.com/questions/1569102/how-to-associate-a-windows-application-with-a-particular-file-type-but-share-tha/1569619#1569619](https://stackoverflow.com/questions/1569102/how-to-associate-a-windows-application-with-a-particular-file-type-but-share-tha/1569619#1569619)

 如果有更好的办法欢迎提出。

   
 