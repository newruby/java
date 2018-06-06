JAVA多线程编程核心技术


之前是
```java
Thread t = new MyThread();
//变成
MyThread t = new MyThread();


//main中
t.setName("t");
// MyThread中
public MyThread(String name) {
        super();
        this.setName(name);
}
//or
public MyThread(String name) {
        super(name);
}

```

## 1.7.2 判断线程是否是停止状态 

interrupted() 静态方法，判断```当前线程```是否已经中断 



```java
Thread.currentThread().interrupt();

System.out.println("is interupted 1?" + Thread.interrupted());
System.out.println("is interupted 2?" + Thread.interrupted());

//true
//false

``` 

interrupted()具有清除状态标志的功能，线程的中断状态由该方法清除，第二次调用后返回false
```java
Thread thread = new Thread();
...
thread.interrupt();

System.out.println("is interupted 1?" + Thread.isInterrupted());
System.out.println("is interupted 2?" + Thread.isInterrupted());

//true
//true

``` 
isInterrupted() 非静态，测试当前线程Thread对象 是否已经是中断状态，不清除状态标志









# JAVA并发编程实战  

## ch1
## **线程的优势**  

提高资源利用率及系统吞吐率