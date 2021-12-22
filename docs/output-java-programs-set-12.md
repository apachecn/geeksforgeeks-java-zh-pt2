# Java 程序输出|第 12 集

> 原文:[https://www.geeksforgeeks.org/output-java-programs-set-12/](https://www.geeksforgeeks.org/output-java-programs-set-12/)

**1)以下程序的输出是什么？** 

```java
public class Test implements Runnable
{
    public void run()
    {
        System.out.printf("%d",3);
    }
    public static void main(String[] args) throws InterruptedException
    {
        Thread thread = new Thread(new Test());
        thread.start();
        System.out.printf("%d",1);
        thread.join();
        System.out.printf("%d",2);
    }

}
```

a)123
b)213
c)132
d)321

```java
Ans: (c)
```

**解释:**父线程等待新创建的线程使用 join 完成。 [join()](https://www.geeksforgeeks.org/joining-threads-in-java/) 方法允许一个线程等待另一个线程完成它的执行。因此，父线程打印 1 并等待子线程完成。子线程在控制台上打印 3，最后父线程打印 2。

**2)以下程序的输出是什么？** 

```java
public class Test
{
    private static int value = 20;
    public int s = 15;
    public static int temp = 10;  
    public static class Nested
    {  
      private void display()
      {
          System.out.println(temp + s + value);
      }  
    }  

    public static void main(String args[])
    {  
      Test.Nested inner = new Test.Nested();  
      inner.display();  
    } 
}
```

a)编译错误
b) 1020
c) 101520
d)以上都没有

```java
Ans: (a)
```

**说明:**非静态变量不能在[静态嵌套内部类](https://www.geeksforgeeks.org/inner-class-java/)中访问。“嵌套”不能访问非静态变量[这种情况下是变量 s]。因此，错误是:

```java
10: error: non-static variable s cannot be referenced from a static context
            System.out.println(temp + s + value);
                                      ^
```

**3)以下程序的输出是什么？** 

```java
import java.io.*;
public class Test
{
    public void display() throws IOException
    {
        System.out.println("Test");
    }

}

class Derived extends Test
{
    public void display() throws IOException
    {
        System.out.println("Derived");
    }
    public static void main(String[] args) throws IOException
    {
        Derived object = new Derived();
        object.display();
    }
}
```

a)测试
b)导出
c)编译错误
d)运行时错误

```java
Ans: (b)
```

**说明:**如果超类方法声明异常，子类被覆盖的方法可以声明相同、子类异常或无异常，但不能声明父异常。

**4)以下程序的输出是什么？** 

```java
public class Test extends Thread
{
    public void run()
    {
        System.out.printf("Test ");
    }
    public static void main(String[] args)
    {
        Test test = new Test();
        test.run();
        test.start();
    }
}
```

a)编译错误
b)运行时错误
c)测试
d)测试测试

```java
Ans: (d)
```

**说明:** test.run()执行 run 方法。test.start()创建一个新线程，并执行 thread 类的重写运行方法。Thread.start()方法总是启动一个新的线程，这个线程的入口点是 run()方法。如果您直接调用 run()，它将在同一个线程中执行，但是**总是建议**逻辑上调用 Thread.start()来启动一个新的执行线程，后跟 run()方法。

**5)以下程序的输出是什么？** 

```java
public class Test extends Thread
{
    public static void main(String[] args)
    {
        String a = "GeeksforGeeks";
        String b = new String(a);
        int value = 0;
        value = (a==b) ? 1:2;
        if(value == 1)
        {
            System.out.println("GeeksforGeeks");
        }
        else if(value == 2)
        {
            System.out.println("Geeks for Geeks");
        }
        else
        {
            System.out.println("GFG");
        }

    }
}
```

a)极客暴发户
b)极客的极客
c) GFG
d)以上都不是

```java
Ans: (b) 
```

**解释:** ==运算符检查两个变量是否引用同一个对象。这里的 a 和 b
指的是两个不同的物体。？:是 if else 语句的另一种形式，可以理解为，条件:如果为真，则执行此操作:else 执行此操作。

**6)以下程序的输出是什么？** 

```java
public class Test
{
    try
    {
        public Test()
        {
            System.out.println("GeeksforGeeks");
            throw new Exception();
        }
    }
    catch(Exception e)
    {
        System.out.println("GFG");
    }
    public static void main(String[] args)
    {
        Test test = new Test();
    }
}
```

a)极客伪造
b) GFG
c)编译错误
d)以上都不是

```java
Ans: (c)
```

**说明:** [构造函数](https://www.geeksforgeeks.org/constructors-in-java/)不能包含在 try/catch 块中。

**7)对于给定的代码，选择正确的答案。** 

```java
public interface Test
{
    public int calculate();
    protected interface NestedInterface
    {
        public void nested();
    }
}
```

a)由于嵌套接口
导致的编译时错误 b)由于嵌套接口
的访问修饰符导致的编译时错误 c)无编译时错误
d)嵌套接口不能保存任何函数声明。

```java
Ans: (b)
```

**说明:**nested interface 的访问修饰符只能是公共的。因此，错误是:

```java
4: error: illegal combination of modifiers: public and protected
    protected interface NestedInterface
              ^
1 error
```

**8)关于构造函数声明，以下哪一项是正确的？** 
a)构造函数可以被声明为最终的。
b)施工人员可以被试/抓块包围。
c)构造函数不能抛出异常。
d)构造函数可以保存同步的代码(这样每个线程都可以顺序访问构造函数)。

```java
Ans: (d)
```

**解释:**构造函数允许线程之间顺序访问数据。

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。