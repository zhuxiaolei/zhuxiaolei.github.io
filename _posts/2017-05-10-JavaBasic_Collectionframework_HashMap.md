---
layout: post
title: "Java 基础 集合框架之HashMap实现原理"
date: 2017-05-10 
description: "Java 基础 集合框架之HashMap实现原理"
tag: JAVA 
---  
 
## 正文：
　HashMap 是基于哈希表的 Map 接口的非同步实现
  允许使用 null 值和 null 键

### 数据结构　JDK7 get复杂度O(n)

<div align="center">
	<img src="/images/posts/java-basic/Collectionframework/HashMap/hashmap.jpg" height="300" width="800">  
</div>

HashMap 在底层将 key-value 当成一个整体进行处理，这个整体就是一个 Entry 对象。HashMap 底层采用一个 Entry[] 数组来保存所有的 key-value 对，当需要存储一个 Entry 对象时，会根据 hash 算法来决定其在数组中的存储位置，在根据 equals 方法决定其在该数组位置上的链表中的存储位置；当需要取出一个Entry 时，也会根据 hash 算法找到其在数组中的存储位置，再根据 equals 方法从该位置上的链表中取出该Entry。


当我们 put 的时候，如果 key 存在了，那么新的 value 会代替旧的 value，并且如果 key 存在的情况下，该方法返回的是旧的 value，如果 key 不存在，那么返回 null。 
从上面的源代码中可以看出：当我们往 HashMap 中 put 元素的时候，先根据 key 的 hashCode 重新计算 hash 值，根据 hash 值得到这个元素在数组中的位置（即下标），如果数组该位置上已经存放有其他元素了，那么在这个位置上的元素将以链表的形式存放，新加入的放在链头，最先加入的放在链尾。如果数组该位置上没有元素，就直接将该元素放到此数组中的该位置上。

### 数据结构 JDK8 get复杂度O(log2n)

<div align="center">
	<img src="/images/posts/java-basic/Collectionframework/HashMap/HashMapjdk8.jpg" height="300" width="800">  
</div>

HashMap类中有一个非常重要的字段，就是 Node[] table，即哈希桶数组，明显它是一个Node的数组
Node是HashMap的一个内部类，实现了Map.Entry接口，本质是就是一个映射(键值对)。上图中的每个黑色圆点就是一个Node对象。

### Hash算法--->链地址法（拉链法）
	
	//取key 的hashCode值 高位参与运算
	static final int hash(Object key) {      //jdk1.8的源码
        int h;
        return (key == null) ? 0 : (h = key.hashCode()) ^ (h >>> 16);
    }
    //除模取余
    static int indexFor(int h, int length) {  //jdk1.7的源码，jdk1.8没有这个方法，但是实现原理一样的
     	return h & (length-1); 
	}


### 性能参数 
	
HashMap 包含如下几个构造器：

* HashMap() 构建一个初始容量为 16 （DEFAULT_INITIAL_CAPACITY = 1 << 4; // aka 16），负载因子为0.75的HashMap.
* HashMap(int initialCapacity) 构建一个初始容量为initialCapacity, 负载因子为0.75的HashMap.
* HashMap(int initialCapacity, float loadFactor) 构建一个指定初始容量、指定负载因子的HashMap.

负载因子loadFactor衡量的是一个散列表的空间使用程度，负载因子越大表示散列表的装填程度越高，反之越小。
对于使用链表法的散列表来说，查找一个元素的平均时间 O（1+a）,因此如果负载因子越大，对空间的利用更充分，然而后果是查找效率的降低；
如果负载因子太小，散列表的数据将过于稀疏，对空间造成严重浪费。

解释：threshold 临界值 initialCapacity的最小2次幂

#### JDK7
	threshold = initialCapacity;

#### JDK8
	this.threshold = tableSizeFor(initialCapacity);

	static final int tableSizeFor(int cap) {
        int n = cap - 1;
        n |= n >>> 1;
        n |= n >>> 2;
        n |= n >>> 4;
        n |= n >>> 8;
        n |= n >>> 16;
        return (n < 0) ? 1 : (n >= MAXIMUM_CAPACITY) ? MAXIMUM_CAPACITY : n + 1;
    }

    补充一下JAVA移位运算符：<<（左移）、>>（带符号右移）和>>>（无符号右移）
    左移的规则只记住一点：丢弃最高位(符号位同样丢弃)，0补最低位
    右移的规则只记住一点：符号位不变，左边补上符号位
    无符号右移的规则只记住一点：忽略了符号位扩展，0补最高位

    public static void main(String[] args) {
		int MAXIMUM_CAPACITY = 1 << 30;
		
		int n = 16 - 1;
		System.out.println("n: " + n + " 二进制: " + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n))) + " 无符号右移二进制：" + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n >>> 1))));
        n |= n >>> 1;
		System.out.println("n: " + n + " 二进制: " + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n))) + " 无符号右移二进制：" + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n >>> 2))));
        n |= n >>> 2;
        System.out.println("n: " + n + " 二进制: " + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n))));
        n |= n >>> 4;
        System.out.println("n: " + n + " 二进制: " + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n))));
        n |= n >>> 8;
        System.out.println("n: " + n + " 二进制: " + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n))));
        n |= n >>> 16;
        System.out.println("n: " + n + " 二进制: " + String.format("%08d",Integer.parseInt(Integer.toBinaryString(n))));
        System.out.println("最后大小：" + ((n < 0) ? 1 : (n >= MAXIMUM_CAPACITY) ? MAXIMUM_CAPACITY : n + 1));
	}

	n: 15 二进制: 00001111 无符号右移二进制：00000111
	n: 15 二进制: 00001111 无符号右移二进制：00000011
	n: 15 二进制: 00001111
	n: 15 二进制: 00001111
	n: 15 二进制: 00001111
	n: 15 二进制: 00001111
	最后大小：16

当put的时候超过这个threshold，就会resize() 容量增至2倍

### Fail-Fast机制

我们知道 java.util.HashMap 不是线程安全的，因此如果在使用迭代器的过程中有其他线程修改了 map，那么将抛出 ConcurrentModificationException，这就是所谓 fail-fast 策略。  
Fail-fast 机制是 java 集合(Collection)中的一种错误机制。 当多个线程对同一个集合的内容进行操作时，就可能会产生 fail-fast 事件。

### 遍历效率高方式

	Map map = new HashMap();
	Iterator iter = map.entrySet().iterator();
	while (iter.hasNext()) {
		Map.Entry entry = (Map.Entry) iter.next();
		Object key = entry.getKey();
		Object val = entry.getValue();
	}

### 如何线程安全的使用HashMap

	//Hashtable
	Map<String, String> hashtable = new Hashtable<>();
 
	//synchronizedMap
	Map<String, String> synchronizedHashMap = Collections.synchronizedMap(new HashMap<String, String>());
 
	//ConcurrentHashMap
	Map<String, String> concurrentHashMap = new ConcurrentHashMap<>();

转载请注明原地址，朱肖磊的博客：[http://zhuxiaolei.github.io](http://zhuxiaolei.github.io) 谢谢！