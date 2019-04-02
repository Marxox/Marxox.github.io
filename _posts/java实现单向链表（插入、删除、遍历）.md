---
title: java实现单向链表（插入、删除、遍历）
date: 2019-03-11 21:19:41
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/88409985   
  创建两个类：LinkList（链表类）和 LinkNode（结点类）。

 LinkList：

 
```
 package singlyLinkedList;
import java.util.Arrays;
import java.util.Scanner;

public class LinkList {
    LinkNode head;
    public LinkList(){
        head=new LinkNode();
        head.next=null;
    }

    /**
     * 创建链表
     */
    public void Sort_Create(){
        System.out.println("创建链表，请输入链表中各个结点数据域的值;创建结束，请输入-1");
        Scanner sc=new Scanner(System.in);
        LinkNode s;//结点
        int[] a=new int[20];//未初始化数组的默认初始值为0
        int c=0;//数组下标
        //将输入的值存到数组中
        for(int num=sc.nextInt();num!=-1;num=sc.nextInt()) {
            a[c++]=num;//每插入一个结点，c自增1
        }
        for (int i = c;i < 20;i++){
            a[i] = Integer.MIN_VALUE;//将int类型的最小值赋给数组中未初始化的值，即0 ---> -2147483648，避免数组的排序被未初始化数组的默认初始值“0”干扰
        }
        Arrays.sort(a);//数组a排序（升序）
        for(int i=20-c;i<20;i++){
            s=new LinkNode();
            s.data=a[i];
            Insert(s);
        }
    }

    /**
     * 在链表中查找恰当的位置，将结点n插入到当前链表中，插入后链表依然有序。
     */
    public void Insert(LinkNode n) {
        LinkNode p = head;
        if (p.next == null) {   //只有一个节点（头结点）
            n.next = p.next;
            p.next = n;         //插入结点n
        } else {
            while (p.next.data <= n.data) {//头结点后的数据小于将要插入的节点的数据。节点的数据已经过升序排序，并按照从小到大的顺序插入结点，所以不考虑大于的情况
                if (p.next.next != null) {
                    p = p.next;//p指向下一个节点的数据域。直到p.next.next为null，插入结点n
                } else {
                    n.next = p.next.next;
                    p.next.next = n; //插入结点n
                    break;
                }
            }
        }
    }

    /**
     * 打印链表上各个结点的数据域的值（遍历链表）
     */
    public void PrintList(){
        System.out.print("链表中各个结点的数据域的值为:");
        LinkNode p;
        p=head.next;
        if(p==null){
            System.out.print("空");
        }
        while(p!=null){
            p.DisplayLinkNode();
            p=p.next;
        }
        System.out.println();
    }

    /**
     * 在当前链表中查找数据域的值为num的结点，将该结点删除
     */
    void Delete_one_node(int num){
        LinkNode p=head,q;
        while(p.next.data!=num){      //定位到删除结点的前驱
            p=p.next;
        }
        q=p.next;           //q指向将要删除的结点
        p.next=q.next;      //删除数据域的值为num的结点
    }

    public static void main(String[] args){
        LinkList linkList=new LinkList();
        linkList.Sort_Create();
        linkList.PrintList();
        System.out.print("请输入需要删除结点的数据域的值:");
        Scanner sc=new Scanner(System.in);
        int num=sc.nextInt();
        linkList.Delete_one_node(num);
        System.out.print("删除数据域的值为“" + num + "”的结点后，");
        linkList.PrintList();
    }
}
```
 LinkNode：

 
```
 package singlyLinkedList;

public class LinkNode {
    public int data;//结点的数据域
    public LinkNode next;//链表中对下一个结点的引用
    public LinkNode(){

    }
    public void DisplayLinkNode(){
        System.out.print(data+" ");
    }
}
```
 运行截图：

 ![](https://img-blog.csdnimg.cn/2019031123463248.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQwMjk5MTY2,size_16,color_FFFFFF,t_70)

   
 