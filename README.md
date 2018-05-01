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