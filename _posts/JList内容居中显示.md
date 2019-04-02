---
title: JList内容居中显示
date: 2018-12-03 10:47:10
tags: CSDN迁移
---
  ```
 DefaultListCellRenderer renderer = new DefaultListCellRenderer();
renderer.setHorizontalAlignment(SwingConstants.CENTER);
jList.setCellRenderer(renderer);
```
 需要让JList中的内容向哪边对齐，修改上述代码中的“CENTER”为对齐的方向就行。

 这个方法是在[http://tieba.baidu.com/p/5128954644](http://tieba.baidu.com/p/5128954644) （2楼）看到的。

 仅作记录收藏。

   
 