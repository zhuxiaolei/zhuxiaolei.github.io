---
layout: post
title: "Java 基础 实现a + b 不用 + "
date: 2017-05-10 
description: "Java 基础 实现a + b 不用 + "
tag: JAVA 
---  
 
## 正文：
　1. A + B 问题
给出两个整数 a 和 b , 求他们的和。

样例
样例  1:
	输入:  a = 1, b = 2
	输出: 3
	
	样例解释: 
	返回a+b的结果.

样例 2:
	输入:  a = -1, b = 1
	输出: 0
	
	样例解释: 
	返回a+b的结果.

挑战
显然你可以直接 return a + b，但是你是否可以挑战一下不这样做？（不使用++等算数运算符）

说明
a和b都是 32位 整数么？
是的

### 代码

    public class Solution {
        /**
         * @param a: An integer
         * @param b: An integer
         * @return: The sum of a and b 
         */
        public int aplusb(int a, int b) {
            // write your code here
            int c=0;
            int d=0;
            while((a&b)!=0){
                c=a^b;
                d=(a&b)<<1;
                a=c;
                b=d;
            }
            return a|b;
        }
        //递归
        public int aplusb(int a, int b) {
            if ((a&b) == 0)
                return a | b;
            return aplusb(a^b, (a&b)<<1);
        }
    }


### 代码解析

解析:

例如入参 a = 1, b=2

    public int aplusb(1, 2) {
        int c = 0;
        int d = 0;
        //---------------------
        1 = 0001
        2 = 0010
      a&b = 0000 = 0
        //---------------------
        while((0) != 0) {
            //没有进位不会进入此循环.
        }

        //---------------------
        1 = 0001
        2 = 0010
      a|b = 0011 = 3
        //---------------------
        return 0001|0002;
    }

例如入参 a = 1, b=3

    public int aplusb(1, 2) {
        int c = 0;
        int d = 0;
        //---------------------
        1 = 0001
        3 = 0011
      a&b = 0001 = 1
        //---------------------
        while((1) != 0) {
            //有进位进入此循环
            c = a^b;
            //-------------
                0001
                0011
        c = a^b=0010 = 2 //抛出去进位
            d = (a&b)<<1; //左移1位
                0001
                0011
          (a&b)=0001 = 1
        0001<<1=0010 = 2
            d = 0010 = 2
            a = 0010 = 2;
            b = 0010 = 2;
            //继续循环 第二次进入while循环

            0010
            0010
        a&b=0010 = 2 != 0   
            //进入循环
            c = a^b;
                0010
                0010
        c = a^b=0000 = 0;
            d = (a&b)<<1;
                0010
                0010
          (a&b)=0010 = 2;
        0010<<1=0100 = 4;
            a = c = 0000 = 0;
            b = d = 0100 = 4;
            //第三次判断while循环
                 0000
                 0100
             a&b=0000 = 0 //不在进入循环； 
            //跳出while循环
                          0000
                          0100
            //return a|b =0100 = 4; 
            //-------------
        }

        //---------------------
        1 = 0001
        2 = 0010
      a|b = 0011 = 3
        //---------------------
        return 0001|0010;
    }



转载请注明原地址，朱肖磊的博客：[http://zhuxiaolei.github.io](http://zhuxiaolei.github.io) 谢谢！