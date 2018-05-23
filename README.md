**CH1基础**
===
入门级书籍：*An Introduction to Programming in Java*  


**Java语言基础（五种语法 ）**
--- 

*   原始数据类型  
    * 整数、浮点数和布尔值  
* 语句  
     * 声明、赋值、条件、循环、调用和返回
* 数组 
* 静态方法  
* 字符串  
* 标准输入/输出 
* 数据抽象  
---

"![ex](/image/tu1.1.1.jpg "java程序及其命令行的调用")"

1.1.2原始数据类型及表达式
---  
int、double、｛true、false｝（boolean）、char  
* 初级运算的关键：*运算产生的数据的数据类型和参与运算的数据的数据类型是相同的*  
5 / 3 -> 1  
5.0 / 3.0 -> 1.666667  

**优先级**： * /（%）**>** + -   
>>>! > && > ||  

**类型转换**：提升为高级的数据类型    
>>*(int)3.7 -> 3*

**其他原始类型**：int 表示2^23个不同的值，用32位二进制表示  
*-2^31~+2^31-1*  

64位双精度实数(double)  
异或^  true ^ true -> false
```
64位整数，极其算数运算符(long)   
16位整数(short)
16位字符(char)
8位整数(byte)
32位单精度实数(float)
``` 
1.1.3
---
**模版**形式记法表示JAVA语法  
<>里表示已经定义的语法
```Java
if(<boolean ecpression>) {<block statements>}
```
```Java
while(<boolean ecpression>) {<block statements>}
```
1.1.4简便记法
---
**声明并初始化** 最好在接近首次使用变量的地方声明它并肩声明它并将其初始化并将其初始化（为了限制它的作用域 ）  

**隐式赋值**  
* ++i <=> i = i + 1 **表达式**为 i + 1，类似的--i <=> i = i - 1  
* i++意思相同表达式的值为i的值
* i += 1  

**for循环简化while循环**     
...... 

# Bags，Queues and Stacks    
 
*原书1.2.2.3*  --   调整数组的大小

```
使用调整大小的数组实现一个通用堆栈。使用调整大小的数组时，我们动态调整数组的大小，以使它足够大以容纳所有项目，而不会大到浪费太多空间。如果push（）已满 ，我们将数组的大小加倍; 如果pop（）小于四分之一满，我们将数组的大小减半。  

```  

## 对象游离   

java的垃圾回收策略是回收无法被访问的对象的内存。当pop()后被弹出的元素的引用仍保存在数组中仍保存在数组中，当这个元素实际上永远也不会被访问。垃圾回收其无法知道这一点，除非该引用被覆盖。保存一个不需要的对象的引用称为游离。  

```java
为避免对象游离，只需将被弹出的数组元素的值设为null
//从栈顶删除元素
String item = a[--N];
a[N] = null;

这将覆盖无用的引用，并使系统可以在用例使用完被弹出的元素后回收它的内存
```
# 迭代  

在任意可迭代的集合数据类型中需要实现  
> iterator()方法并返回一个Iterator对象   
> Iterator类必须包含两个方法 hasNext()  next()  
实用接口机制来制定一个类所必须实现的方法   

```java
public interface Iterable<Item> {
    Iterator<Item> iterator();
}

public interface Iterator<Item> {
    boolean hasNext();
    Item next();
    void remove();
}
```

```ResizingArrayStack``` 这个泛型可迭代的Sack API的是现实所有集合类抽象数据类型实现的模版  

它将所有元素保存在数组中, 并动态调整数组以保持数组大小和栈大小之比小于一个常数 

# 链表  

```
一种递归的数据结构，它或者为空(null)或者指向一个结点(node)的引用，该结点含有一个泛型的元素和一个指向另一条链表的引用
```

```java
private class Node {
   Item item; //Item参数类型
   Node next;
}
```  
链接：表示对结点的引用

* 建立一个链表

"![ex](https://algs4.cs.princeton.edu/13stacks/images/linked-list.png "建立一个链表")"  

* 在开始处插入

"![ex](https://algs4.cs.princeton.edu/13stacks/images/linked-list-insert-front.png "在开始处插入")"  

* 从开始删除

"![ex](https://algs4.cs.princeton.edu/13stacks/images/linked-list-remove-first.png "从开始删除")"  


* 在最后插入

"![ex](https://algs4.cs.princeton.edu/13stacks/images/linked-list-insert-end.png "在最后插入")"


**遍历**  

```java
for（Node x = first; x！= null; x = x.next）{
   //处理x.item
}
```




实现任意插入和删除操作的解决方案是双向链表 