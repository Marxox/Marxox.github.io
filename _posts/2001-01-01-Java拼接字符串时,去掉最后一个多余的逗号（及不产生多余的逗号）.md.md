---
title: Java拼接字符串时,去掉最后一个多余的逗号（及不产生多余的逗号）
date: 2018-11-20 05:04:00
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/84268558   
  作者初学Java，遇到一道题：

 **已知一个List中存有若干人的姓名，如list=[tom jack smith nickel],要求将list中的所有姓名拼接成一个字符串“tom,jack,smith,nickel”**

 在拼接字符串时，可能会在字符串最后多出一个逗号。下面注释中提供了两种解决方法。有错误或不完善之处欢迎提出来。

 
```
 package com.java;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class TestFour {
	public static void main(String[] args) {
		List list = new ArrayList();
		list.add("tom");
		list.add("jack");
		list.add("smith");
		list.add("nickel");
/* 去掉最后一个多余的逗号
		String s = "";
		Iterator it = list.iterator();
		while(it.hasNext()){
			String o = (String)it.next();
			s += o + ",";
			if(!it.hasNext()){
				StringBuffer s1 = new StringBuffer(s);
				s1 = s1.deleteCharAt(s1.length() - 1);
				s = s1.toString();
			}
		}
		System.out.print(s);
*/

		
/* 不产生多余的逗号
		StringBuffer s = new StringBuffer();
		Iterator it = list.iterator();
		while(it.hasNext()){
			Object o = it.next();
			if(s.length() > 0){
				s.append(",");
				s.append(o);
			} else{
				s.append(o);
			}	
		}
		String ss = s.toString();
		System.out.println(ss);
*/
	}
}

```
 
--------

### 2019.3.10更新

 统计字符串中各单词出现的次数，例如：字符串为“java,java,j2ee,ibm,j2ee,ibm,j2me,java”，结果为“j2me-1个；java-3个；ibm-2个；j2ee-2个”

 
```
 package com.first;

import org.apache.commons.lang3.StringUtils;// http://commons.apache.org/proper/commons-lang/download_lang.cgi

import java.util.HashMap;
import java.util.Map;

public class CountWords {
    public static void main(String[] args) {
        String str = "java,java,j2ee,ibm,j2ee,ibm,j2me,java";
        String[] arr = str.split(",");//字符串转为数组，用“,”分割
        Map<String,Integer> map = new HashMap<>();//以单词作为key，出现次数作为value，存进Map
        /*
         *遍历数组，判断Map中是否存在此单词。不存在，则将该单词存进去，value为1；存在，则将value加1。
         */
        for (String e : arr) {
            if (map.get(e) == null){
                map.put(e,1);
            }else{
                map.put(e,map.get(e) + 1);
            }
        }
        int size = map.keySet().size();    //下面要创建一个数组，这里先获得数组的长度
        String[] strArr = new String[size];
        int index = 0;//数组下标
        for (Object e : map.keySet()) {
            strArr[index] = e + "-" + map.get(e) + "个";//将遍历Map的结果存进数组，为了不产生多余的符号
            index++;
        }
        System.out.println(StringUtils.join(strArr,"；"));//将数组转为字符串，用“,”分割
    }
}

```
 通过“StringUtils.join(数组,分隔符)”输出字符串，避免产生多余符号。调用此方法需要引入“commons-lang3”包，可以去[https://www-eu.apache.org/dist//commons/lang/binaries/commons-lang3-3.8.1-bin.zip](https://www-eu.apache.org/dist//commons/lang/binaries/commons-lang3-3.8.1-bin.zip)下载3.8.1版本的jar包。

 或者[http://commons.apache.org/proper/commons-lang/download_lang.cgi](http://commons.apache.org/proper/commons-lang/download_lang.cgi)

   
 