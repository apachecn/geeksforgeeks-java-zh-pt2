# Java 中的读写锁接口

> 原文:[https://www . geesforgeks . org/readwritelock-interface-in-Java/](https://www.geeksforgeeks.org/readwritelock-interface-in-java/)

锁是一种设备，用于命令多个线程访问分配的资源。通常，锁授予对共享资源的独占访问权:一次只有一个线程可以获取锁，每个访问共享资源的人都要求先获取锁。但是，有些锁可能允许并行访问共享资源，如读写锁的读锁。

读写锁是一个接口。读写锁由[Java . util . concurrent . lock](https://www.geeksforgeeks.org/java-util-concurrent-package/)包中的[retrantreadwritelock](https://www.geeksforgeeks.org/reentrant-lock-java/)类实现。因此，要使用读写锁，我们必须使用重入读写锁。

一个 Java . util . concurrent . lock . read write lock 是一个高级线程锁工具。它允许不同的线程读取特定的资源，但一次只允许一个线程写入。

方法是，多个线程可以从一个共享资源中读取，而不会导致并发错误。当对共享资源的写入和读取同时发生时，或者当多个写入同时发生时，首先出现并发错误。

**规则:**

读锁和写锁，允许线程锁定读写锁进行读取或写入。

1.  **读锁:**如果没有线程请求写锁和写锁，那么多个线程可以锁定读锁。这意味着只要没有线程写入数据或更新数据，多个线程就可以在此时读取数据。
2.  **写锁:**如果没有线程正在写或读，一次只有一个线程可以锁锁写。其他线程必须等到锁被释放。这意味着，此时只有一个线程可以写入数据，其他线程必须等待。

**方法:**读写锁提供两种方法:

1.  锁定读取锁定()
2.  锁定写锁定()

他们的工作和他们的名字相似。readLock()用于在读取时获取锁:

```java
Lock readLock = rwLock.readLock();
```

对执行读取操作的代码块使用读锁定:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
readLock.lock();
try {
   // statements 
} 
finally {
   readLock.unlock();
}
```

并且，writeLock()用于在写入时获取锁:

```java
Lock writeLock = rwLock.writeLock();
```

对执行写操作的代码块使用写锁定:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
writeLock.lock();
try {
    statements to write the data
} 
finally {
    writeLock.unlock();
}
```

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Implementation of ReadWriteLock in Java
import java.io.*;
import java.util.ArrayList;
import java.util.List;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReadWriteLock;
import java.util.concurrent.locks.ReentrantReadWriteLock;
class GFG<O> {

    private final ReadWriteLock readWriteLock
        = new ReentrantReadWriteLock();
    private final Lock writeLock
        = readWriteLock.writeLock();
    private final Lock readLock = readWriteLock.readLock();
    private final List<O> list = new ArrayList<>();

    // setElement function sets
    // i.e., write the element to the thread
    public void setElement(O o)
    {
        // acquire the thread for writing
        writeLock.lock();
        try {
            list.add(o);
            System.out.println(
                "Element by thread "
                + Thread.currentThread().getName()
                + " is added");
        }
        finally {
            // To unlock the acquired write thread
            writeLock.unlock();
        }
    }

    // getElement function prints
    // i.e., read the element from the thread
    public O getElement(int i)
    {
        // acquire the thread for reading
        readLock.lock();
        try {
            System.out.println(
                "Elements by thread "
                + Thread.currentThread().getName()
                + " is printed");
            return list.get(i);
        }
        finally {
            // To unlock the acquired read thread
            readLock.unlock();
        }
    }
    public static void main(String[] args)
    {
        GFG<String> gfg = new GFG<>();

        gfg.setElement("Hi");
        gfg.setElement("Hey");
        gfg.setElement("Hello");

        System.out.println("Printing the last element : "
                           + gfg.getElement(2));
    }
}
```

**Output**

```java
Element by thread main is added
Element by thread main is added
Element by thread main is added
Elements by thread main is printed
Printing the last element : Hello
```