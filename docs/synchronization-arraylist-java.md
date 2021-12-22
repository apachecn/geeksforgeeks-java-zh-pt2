# Java 中数组列表的同步

> 原文:[https://www . geesforgeks . org/synchronization-ArrayList-Java/](https://www.geeksforgeeks.org/synchronization-arraylist-java/)

默认情况下，数组列表的实现不同步。这意味着如果一个线程在结构上修改它，并且多个线程同时访问它，那么它必须在外部同步。结构修改意味着从列表中添加或删除元素，或者显式调整支持数组的大小。更改现有元素的值不是结构修改。

**创建同步数组列表有两种方法。**

1.Collections.synchronizedList()方法。
2。使用 CopyOnWriteArrayList。

### 方法 1:使用 Collections.synchronizedList()方法

要进行串行访问，必须通过返回的列表完成对后备列表的所有访问。用户**在迭代返回的列表时，必须手动**对其进行同步。

```java
public static  List<T> synchronizedList(List<T> list)
```

*   接受一个列表，该列表可以是**列表**界面的实现。例如数组列表、链接列表。
*   返回由指定列表支持的同步(线程安全)列表。
*   参数列表是要包装在同步列表中的列表。
*   t 代表[通用](https://www.geeksforgeeks.org/generics-in-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of
// Collections.synchronizedList

import java.util.*;

class GFG
{
    public static void main (String[] args)
    {
        List<String> list =
           Collections.synchronizedList(new ArrayList<String>());

        list.add("practice");
        list.add("code");
        list.add("quiz");

        synchronized(list)
        {
            // must be in synchronized block
            Iterator it = list.iterator();

            while (it.hasNext())
                System.out.println(it.next());
        }
    }
}
```

**Output**

```java
practice
code
quiz
```

### 方法 2:使用 CopyOnWriteArrayList

```java
CopyOnWriteArrayList<T> threadSafeList = new CopyOnWriteArrayList<T>();
```

*   创建一个空列表。
*   实现**列表**界面。
*   它是数组列表的线程安全变体。
*   t 代表泛型

数组列表的线程安全变体，其中所有的变异操作(例如，添加、设置、移除..)是通过创建底层**数组**的单独副本来实现的。它通过创建一个单独的列表副本来实现线程安全，该副本不同于用于提供线程安全的 vector 或其他集合。

*   当您不能或不想**同步**遍历但需要防止并发线程之间的干扰时，这很有用。
*   由于每次写入操作(例如，添加、设置、删除)都涉及单独的**阵列拷贝**，因此**成本很高。)**
*   当你有**列表**需要遍历它的元素并且不经常修改的时候，效率非常高。

迭代器不会抛出**ConcurrentModificationException**，即使一旦创建了迭代器，copyOnWriteArrayList 就会被修改。当对数组列表的另一个副本进行写操作时，迭代器正在对数组列表的单独副本进行迭代。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the thread-safe ArrayList.

import java.io.*;
import java.util.Iterator;
import java.util.concurrent.CopyOnWriteArrayList;

class GFG
{
    public static void main (String[] args)
    {
        // creating a thread-safe Arraylist.
        CopyOnWriteArrayList<String> threadSafeList
            = new CopyOnWriteArrayList<String>();

        // Adding elements to synchronized ArrayList
        threadSafeList.add("geek");
        threadSafeList.add("code");
        threadSafeList.add("practice");

        System.out.println("Elements of synchronized ArrayList :");

        // Iterating on the synchronized ArrayList using iterator.
        Iterator<String> it = threadSafeList.iterator();

        while (it.hasNext())
            System.out.println(it.next());
    }
}
```

**Output**

```java
Elements of synchronized ArrayList :
geek
code
practice
```

**如果我们试图通过** **迭代器的方法修改 CopyOnWriteArrayList，会发生什么？**

如果您试图通过迭代器自己的方法(例如 add()、set()、remove())修改**copy onwriterarraylist**，它将引发 UnsupportedOperationException。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the thread-safe ArrayList

import java.io.*;
import java.util.Iterator;
import java.util.concurrent.CopyOnWriteArrayList;

class GFG
{
    public static void main (String[] args)
    {
        // creating a thread-safe Arraylist.
        CopyOnWriteArrayList<String> threadSafeList =
            new CopyOnWriteArrayList<String>();

        // Adding elements to synchronized ArrayList
        threadSafeList.add("geek");
        threadSafeList.add("code");
        threadSafeList.add("practice");

        System.out.println("Elements of synchronized ArrayList :");

        // Iterating on the synchronized ArrayList using iterator.
        Iterator<String> it = threadSafeList.iterator();

        while (it.hasNext())
        {
            String str = it.next();
            it.remove();
        }
    }
}
```

**运行时错误:**

```java
Exception in thread "main" java.lang.UnsupportedOperationException
    at java.util.concurrent.CopyOnWriteArrayList$COWIterator.remove
        (CopyOnWriteArrayList.java:1176)
    at GFG.main(File.java:28)
```

### CopyOnWriteArrayList 的其他构造函数

1.**copy onwriterarraylist(集合<？扩展 E > c)** :创建一个包含指定集合元素的列表，按照集合迭代器返回元素的顺序。

2.**copy onwriterarraylist(E[]to copy in)**:创建一个包含给定数组副本的列表。

**向量同步时为什么要用 ArrayList？**

1.  **性能:** Vector 是**同步的**和线程安全的，正因为如此，它比 ArrayList 稍慢。
2.  **功能:**矢量在每个单独操作的级别上同步。一般来说，程序员喜欢同步整个操作序列。同步单个操作既不太安全，也较慢。
3.  **向量过时:**向量在 java 中被认为是过时的，并且被非正式地否决了。此外，向量在几乎从未完成的每个单独操作上同步。大多数 java 程序员更喜欢使用 arrayList，因为如果需要同步，他们可能会显式地同步 ArrayList。

**必读:**[Java 中的向量 vs 数组列表](https://www.geeksforgeeks.org/vector-vs-arraylist-java/)

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。