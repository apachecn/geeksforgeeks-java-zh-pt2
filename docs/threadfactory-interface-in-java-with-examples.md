# Java 线程工厂接口，示例

> 原文:[https://www . geeksforgeeks . org/thread factory-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/threadfactory-interface-in-java-with-examples/)

**java.util.concurrent** 包中定义的**线程工厂**接口基于[工厂设计模式](https://www.geeksforgeeks.org/factory-method-design-pattern-in-java/)。顾名思义，它用于按需创建新线程。可以通过两种方式创建线程:

**1。创建一个扩展****类的类，然后创建它的对象。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;

class GFG {

    public static void main(String[] args)
    {
        // Creating a thread
        Thread thread = new CustomThread();
        thread.start(); // Starting execution of the created
                        // thread
    }
}

// Creating a class that extends the Thread class
class CustomThread extends Thread {
    @Override public void run()
    {
        System.out.println("This is a thread");
    }
}
```

**Output**

```java
This is a thread
```