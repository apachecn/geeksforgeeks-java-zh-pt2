# 线程安全以及如何在 Java 中实现

> 原文:[https://www . geesforgeks . org/thread-safety-and-how-to-it-in-Java/](https://www.geeksforgeeks.org/thread-safety-and-how-to-achieve-it-in-java/)

我们知道 Java 有一个特性，[多线程](https://www.geeksforgeeks.org/multithreading-in-java/)，这是一个同时运行多个线程的过程。当多个线程在处理同一个数据，并且我们的数据值在变化时，这种情况不是线程安全的，我们会得到不一致的结果。当一个线程已经在处理一个对象，并阻止另一个线程处理同一个对象时，这个过程称为线程安全。

### **如何实现螺纹安全**

在 [Java](https://www.geeksforgeeks.org/java-programming-basics/) 中实现线程安全有四种方式。这些是:

1.  使用[同步](https://www.geeksforgeeks.org/synchronized-in-java/)。
2.  使用[挥发关键字](https://www.geeksforgeeks.org/volatile-keyword-in-java/)。
3.  使用[原子变量](https://www.geeksforgeeks.org/atomic-variables-in-java-with-examples/)。
4.  使用[最终关键字](https://www.geeksforgeeks.org/final-keyword-java/)。

### **使用同步**

同步是一次只允许一个线程完成特定任务的过程。这意味着当多个线程同时执行，并且想同时访问同一个资源时，就会出现不一致的问题。因此，同步通过一次只允许一个线程来解决不一致性问题。
同步使用*同步关键词*。Synchronized 是一个修饰符，它创建了一个被称为临界区的代码块。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class A {
    synchronized void sum(int n)
    {

        // Creating a thread instance
        Thread t = Thread.currentThread();
        for (int i = 1; i <= 5; i++) {
            System.out.println(
                t.getName() + " : " + (n + i));
        }
    }
}

// Class B extending thread class
class B extends Thread {

    // Creating an object of class A
    A a = new A();
    public void run()
    {

        // Calling sum() method
        a.sum(10);
    }
}
class Test {
    public static void main(String[] args)
    {

        // Creating an object of class B
        B b = new B();

        // Initializing instance t1 of Thread
        // class with object of class B
        Thread t1 = new Thread(b);

        // Initializing instance t2 of Thread
        // class with object of class B
        Thread t2 = new Thread(b);

        // Initializing thread t1 with name
        //'Thread A'
        t1.setName("Thread A");

        // Initializing thread t2 with name
        //'Thread B'
        t2.setName("Thread B");

        // Starting thread instance t1 and t2
        t1.start();
        t2.start();
    }
}
```

**Output:** 

```
Thread A : 11
Thread A : 12
Thread A : 13
Thread A : 14
Thread A : 15
Thread B : 11
Thread B : 12
Thread B : 13
Thread B : 14
Thread B : 15
```

### **使用 Volatile 关键字**

volatile 关键字是一个字段修饰符，它确保对象可以被多个线程同时使用而不会有任何问题。volatile 是确保 Java 程序线程安全的一种好方法。一个 volatile 关键字可以作为在 Java 中实现线程安全的替代方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class VolatileExample {

    // Initializing volatile variables
    // a, b
    static volatile int a = 0, b = 0;

    // Defining a static void method
    static void method_one()
    {
        a++;
        b++;
    }

    // Defining static void method
    static void method_two()
    {
        System.out.println(
            "a=" + a + " b=" + b);
    }

    public static void main(String[] args)
    {

        // Creating an instance t1 of
        // Thread class
        Thread t1 = new Thread() {
            public void run()
            {
                for (int i = 0; i < 5; i++)
                    method_one();
            }
        };

        // Creating an instance t2 of
        // Thread class
        Thread t2 = new Thread() {
            public void run()
            {
                for (int i = 0; i < 5; i++)
                    method_two();
            }
        };

        // Starting instance t1 and t2
        t1.start();
        t2.start();
    }
}
```

**Output:** 

```
a=5 b=5
a=5 b=5
a=5 b=5
a=5 b=5
a=5 b=5
```

### **使用原子变量**

使用原子变量是 java 中实现线程安全的另一种方式。当多个线程共享变量时，原子变量确保线程不会相互碰撞。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.concurrent.atomic.AtomicInteger;

class Counter {

    // Creating a variable of
    // class type AtomicInteger
    AtomicInteger count
        = new AtomicInteger();

    // Defining increment() method
    // to change value of
    // AtomicInteger variable
    public void increment()
    {
        count.incrementAndGet();
    }
}

public class TestCounter {
    public static void main(
        String[] args) throws Exception
    {

        // Creating an instance of
        // Counter class
        Counter c = new Counter();

        // Creating an instance t1 of
        // Thread class
        Thread t1 = new Thread(
            new Runnable() {
                public void run()
                {
                    for (int i = 1; i <= 2000; i++) {
                        c.increment();
                    }
                }
            });

        // Creating an instance t2
        // of Thread class
        Thread t2 = new Thread(
            new Runnable() {
                public void run()
                {
                    for (int i = 1; i <= 2000; i++) {
                        c.increment();
                    }
                }
            });

        // Calling start() method with t1 and t2
        t1.start();
        t2.start();

        // Calling join method with t1 and t2
        t1.join();
        t2.join();

        System.out.println(c.count);
    }
}
```

**Output:** 

```
4000
```

### **使用最终关键字**

Final Variables 在 java 中也是线程安全的，因为一旦分配了某个对象的引用，它就不能指向另一个对象的引用。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class FinalTest {

    // Initializing a string
    // variable of final type
    final String str
        = new String("hello");

    // Defining a method to
    // change the value of the final
    // variable which is not possible,
    // hence the error will be shown
    void method()
    {
        str = "world";
    }
}
```

**输出:**

```
Compilation Error in java code :- 
prog.java:14: error: cannot assign a value to final variable str
        str = "world";
        ^
1 error
```