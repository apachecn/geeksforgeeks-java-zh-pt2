# Java 中的 Thread.sleep()方法，示例

> 原文:[https://www . geesforgeks . org/thread-sleep-in-Java-method-with-examples/](https://www.geeksforgeeks.org/thread-sleep-method-in-java-with-examples/)

[线程类](https://www.geeksforgeeks.org/java-lang-thread-class-java/)是一个基本上是程序执行线程的类。它存在于 [Java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中。线程类包含**睡眠()**方法。Thread 类中存在 Sleep()方法的两个重载方法，一个带有一个参数，另一个带有两个参数。sleep()方法用于在特定的持续时间内停止当前线程(无论哪个线程可能正在系统中执行)的执行，并且在该持续时间结束后，较早执行的线程将再次开始执行。

**关于 Thread.sleep()方法的要点:**

*   方法每当 Thread.sleep()函数要执行时，它总是暂停当前线程的执行。
*   如果任何其他线程在线程休眠时中断，那么将引发中断异常。
*   如果系统繁忙，则线程将休眠的实际时间将比调用 sleep 方法时经过的时间长，如果系统负载较少，则线程的实际休眠时间将接近调用 sleep()方法时经过的时间。

**睡眠()方法的语法**

*   公共静态无效睡眠(长毫秒)引发中断异常
*   公共静态无效睡眠(长毫秒)引发 IllegalArguementException
*   公共静态无效睡眠(长毫秒，整数纳米)引发中断异常
*   公共静态无效睡眠(长毫，int nanos)抛出 IllegalArguementException

**传入线程的参数。睡眠()方法**

*   毫秒:线程将休眠的持续时间(毫秒)
*   nanos:这是我们希望线程休眠的额外时间，单位为纳秒。范围从 0 到 999999。

**返回睡眠类型()方法:**它不返回任何值，即睡眠函数的返回类型无效。

带有一个参数的 sleep 方法是本机方法，即这个方法的实现是用另一种编程语言完成的，而带有两个参数的另一个方法不是本机方法，即它的实现是用 Java 完成的。这两种睡眠方法都是静态的，即我们可以使用线程类来访问它们。这两种方法都抛出一个选中的异常，即我们可以通过使用 throws 关键字或使用 try 和 catch 块来处理异常。

我们可以使用线程。任何线程的 Sleep()方法，即我们可以用主线程或我们以编程方式创建的任何其他线程来实现它。

*   **使用螺纹。主线程休眠()方法**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program for sleeping the main thread.

import java.io.*;
import java.lang.Thread;

class GFG {
    public static void main(String[] args)
    {
        // we can also use throws keyword followed by
        // exception name for throwing the exception

        try {
            for (int i = 0; i < 5; i++) {

                // it will sleep the main thread for 1 sec
                // ,each time the for loop runs
                Thread.sleep(1000);

                // printing the value of the variable
                System.out.println(i);
            }
        }
        catch (Exception e) {

            // catching the exception
            System.out.println(e);
        }
    }
}
```

**Output**

```java
0
1
2
3
4
```

*   **使用螺纹。自定义线程的休眠()方法**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program for sleeping the custom thread.

import java.io.*;
import java.lang.Thread;

class GFG extends Thread {

    public void run()
    {
        // thread 0

        // we can also use throws keyword followed by
        // exception name for throwing the exception
        try {
            for (int i = 0; i < 5; i++) {

                // it will sleep the main thread for 1 sec
                // ,each time the for loop runs
                Thread.sleep(1000);

                // This Thread.sleep() method will sleep the
                // thread 0.
                // printing the value of the variable
                System.out.println(i);
            }
        }
        catch (Exception e) {

            // catching the exception
            System.out.println(e);
        }
    }
    public static void main(String[] args)
    {
        // main thread
        GFG obj = new GFG();
        obj.start();
    }
}
```

**Output**

```java
0
1
2
3
4
```

*   **睡眠时间为负时的异常**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program for showing how exception can occur if we
// pass the negative timeout value.

import java.io.*;
import java.lang.Thread;

class GFG {
    public static void main(String[] args)
    {
        // we can also use throws keyword followed by
        // exception name for throwing the exception

        try {
            for (int i = 0; i < 5; i++) {

                // this will throw the
                // IllegalArgumentException
                Thread.sleep(-100);

                // printing the value of the variable
                System.out.println(i);
            }
        }
        catch (Exception e) {

            // catching the exception
            System.out.println(e);
        }
    }
}
```

**Output**

```java
java.lang.IllegalArgumentException: timeout value is negative
```