---
layout: post
title: "Java基本类型占用字节数"
date: 2017-04-28 
description: "Java 基本类型占用字节数"
tag: JAVA 
---  
 
## 正文：
　1字节=8位(1byte = 8bit)

### 代码　

	public static void main(String[] args) {
		//1字节=8位(1byte = 8bit)
		System.out.println("int     二进制位数: " + Integer.SIZE + " 字节: " + Integer.SIZE/8);
		System.out.println("short   二进制位数: " + Short.SIZE + " 字节: " + Short.SIZE/8);
		System.out.println("long    二进制位数: " + Long.SIZE + " 字节: " + Long.SIZE/8);
		System.out.println("byte    二进制位数: " + Byte.SIZE + "  字节: " + Byte.SIZE/8);
		System.out.println("char    二进制位数: " + Character.SIZE + " 字节: " + Character.SIZE/8);
		System.out.println("float   二进制位数: " + Float.SIZE + " 字节: " + Float.SIZE/8);
		System.out.println("douible 二进制位数: " + Double.SIZE + " 字节: " + Double.SIZE/8);
		System.out.println("boolean : " + Boolean.toString(true));
	}

### 输出
	
	int     二进制位数: 32 字节: 4
	short   二进制位数: 16 字节: 2
	long    二进制位数: 64 字节: 8
	byte    二进制位数: 8  字节: 1
	char    二进制位数: 16 字节: 2
	float   二进制位数: 32 字节: 4
	douible 二进制位数: 64 字节: 8
	boolean : true

转载请注明原地址，朱肖磊的博客：[http://zhuxiaolei.github.io](http://zhuxiaolei.github.io) 谢谢！