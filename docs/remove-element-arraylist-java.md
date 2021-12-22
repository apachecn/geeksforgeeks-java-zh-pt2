# 如何在 Java 中从 ArrayList 中移除一个元素？

> 原文:[https://www . geesforgeks . org/remove-element-ArrayList-Java/](https://www.geeksforgeeks.org/remove-element-arraylist-java/)

ArrayList 是 [**集合框架**](https://www.geeksforgeeks.org/collections-in-java-2/) 的一部分，存在于 java.util 包中。它为我们提供了 Java 中的动态数组。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。这个类可以在[**Java . util**](https://www.geeksforgeeks.org/java-util-package-java/)包中找到。随着 java 版本的引入和升级，更新的方法正在出现，就好像我们确实从 Java8 中看到了感知 lambda 表达式和流概念在 Java 8 版本中引入之前是不可用的，所以我们有更多的方法在 Arraylist 上操作来执行操作。这里我们将讨论一种从数组列表中移除元素的方法。

当从数组列表中移除元素时，我们可以通过索引或数组列表中的值来移除元素。我们将通过一个干净的 java 程序解释来讨论这两种方式。

**方法:**

从数组列表中移除元素有 **3 种方法，如下所示:**

1.  通过索引使用 remove()方法(默认)
2.  通过值使用 remove()方法
3.  在迭代器上使用 remove()方法

> **注意:**迭代元素时不建议使用 ArrayList.remove()。

**方法 1:** 通过索引使用 remove()方法

这是一个默认方法，只要我们在数据结构上使用任何方法，它基本上只在索引上运行，所以每当我们使用 remove()方法时，我们基本上是从数组列表的标记中移除元素。

[ArrayList 类](https://www.geeksforgeeks.org/arraylist-in-java/)提供了两个重载的 remove()方法。

*   [Remove (int index):](https://www.geeksforgeeks.org/list-removeint-index-method-in-java-with-examples/) Accept the index of the object to be removed.
*   [Remove (Object obj):](https://www.geeksforgeeks.org/list-removeobject-obj-method-in-java-with-examples/) Accept the object to be removed.

让我们借助下面提供的例子来搞清楚:

**示例:**

## Java

```
// Java program to Remove Elements from ArrayList
// Using remove() method by indicies

// Importing required classes
import java.util.ArrayList;
import java.util.List;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of List interface with
        // reference to ArrayList class
        List<Integer> al = new ArrayList<>();

        // Adding elements to our ArrayList
        // using add() method
        al.add(10);
        al.add(20);
        al.add(30);
        al.add(1);
        al.add(2);

        // Printing the current ArrayList
        System.out.println(al);

        // This makes a call to remove(int) and
        // removes element 20
        al.remove(1);

        // Now element 30 is moved one position back
        // So element 30 is removed this time
        al.remove(1);

        // Printing the updated ArrayList
        System.out.println(al);
    }
}
```

**输出**

```
[10, 20, 30, 1, 2]
[10, 1, 2]
```

现在我们已经看到通过上面的索引移除数组列表中的元素，现在让我们看到传递的参数被认为是一个索引。如何通过值移除元素？

**方法 2:** 使用按值移除()方法

**例:**

## 爪哇

```
// Java program to Remove Elements from ArrayList
// Using remove() method by values

// Importing required classes
import java.util.ArrayList;
import java.util.List;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of List interface with
        // reference to ArrayList
        List<Integer> al = new ArrayList<>();

        // Adding elements to ArrayList class
        // using add() method
        al.add(10);
        al.add(20);
        al.add(30);
        al.add(1);
        al.add(2);

        // Printing the current ArrayList
        System.out.println(al);

        // This makes a call to remove(Object) and
        // removes element 1
        al.remove(new Integer(1));

        // This makes a call to remove(Object) and
        // removes element 2
        al.remove(new Integer(2));

        // Printing the modified ArrayList
        System.out.println(al);
    }
}
```

**输出:**

```
[10, 20, 30,1 ,2]
[10, 20, 30]
```

> **注意:**迭代元素时不建议使用 ArrayList.remove()。

**方法 3:** 使用迭代器. remove()方法

这可能会导致[ConcurrentModificationException](https://docs.oracle.com/javase/7/docs/api/java/util/ConcurrentModificationException.html)在迭代元素时，建议使用 [Iterator.remove()](https://www.geeksforgeeks.org/iterators-in-java/) 方法。

**示例:**

## Java

```
// Java program to demonstrate working of
// Iterator.remove() on an integer arraylist
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an ArrayList
        List<Integer> al = new ArrayList<>();

        // Adding elements to our ArrayList
        // using add() method
        al.add(10);
        al.add(20);
        al.add(30);
        al.add(1);
        al.add(2);

        // Printing the current ArrayList
        System.out.println(al);

        // Creating iterator object
        Iterator itr = al.iterator();

        // Holds true till there is sibgle element
        // remaining in the object
        while (itr.hasNext()) {

            // Remove elements smaller than 10 using
            // Iterator.remove()
            int x = (Integer)itr.next();
            if (x < 10)
                itr.remove();
        }

        // Printing the updated ArrayList
        System.out.print(al);
    }
}
```

**输出**

```
[10, 20, 30, 1, 2]
[10, 20, 30]
```

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。