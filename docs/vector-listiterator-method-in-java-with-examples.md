# Java 中的向量列表迭代器()方法，示例

> 原文:[https://www . geesforgeks . org/vector-listiterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/vector-listiterator-method-in-java-with-examples/)

<center>

这个方法返回一个列表迭代器，以适当的顺序遍历[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)对象的元素。它是双向的，所以向前和向后遍历都是可能的，分别使用 *next()* 和 *previous()* 。这样返回的迭代器是*快速失效*。这意味着在迭代器创建后，以任何方式从结构上修改向量，除了通过*迭代器自己的*移除或添加方法(使用*向量*)。例如 add()，将导致迭代器抛出**ConcurrentModificationException**。

**语法:**

```
public ListIterator listIterator()

```

**参数:**该方法不接受输入参数。

**返回值:**这个方法返回一个[列表迭代器](https://www.geeksforgeeks.org/iterators-in-java/#ListIterator)对象，可以用来遍历 Vector 对象。

**示例 1:** 使用 listIterator()演示向前和向后遍历。

```
// Java code to illustrate listIterator()

import java.util.Vector;
import java.util.ListIterator;

public class GFG {
    public static void main(String[] args)
    {
        // Declare empty vector
        Vector<String> vt = new Vector<String>();

        vt.add("Geeks");
        vt.add("for");
        vt.add("Geeks");
        vt.add("2019");
        vt.add("AComputerSciencePortalForGeeks");

        // Declare list iterator
        ListIterator listItr = vt.listIterator();

        // Forward iterations
        System.out.println("Forward Traversal:");
        while (listItr.hasNext()) {
            System.out.println(listItr.next());
        }

        // Backward iterations
        System.out.println("\nBackward Traversal:");
        while (listItr.hasPrevious()) {
            System.out.println(listItr.previous());
        }
    }
}
```

**Output:**

```
Forward Traversal:
Geeks
for
Geeks
2019
AComputerSciencePortalForGeeks

Backward Traversal:
AComputerSciencePortalForGeeks
2019
Geeks
for
Geeks

```

<center>

此方法用于通过指定起始索引来返回列表迭代器。也是双向和快速故障。

**语法:**

```
public ListIterator listIterator(int index)

```

**参数:**参数索引是一个整型值，指定从列表迭代器返回的第一个元素(通过调用 *next()* )。

**返回值:**这个方法返回一个[列表迭代器](https://www.geeksforgeeks.org/iterators-in-java/#ListIterator)对象，可以用来遍历 Vector 对象。

**异常:**如果指数超出范围(指数< 0 或指数>大小())，此方法将抛出**指数**

**示例 2:** 演示 listIterator(int index)。

```
// Java code to illustrate listIterator(int index)

import java.util.Vector;
import java.util.ListIterator;

public class GFG {
    public static void main(String[] args)
    {
        // Declare empty vector
        Vector<String> vt = new Vector<String>();

        vt.add("Geeks");
        vt.add("for");
        vt.add("Geeks");

        // Declare list iterator
        ListIterator listItr = vt.listIterator(1);
        // traversal
        while (listItr.hasNext()) {
            System.out.println(listItr.next());
        }
    }
}
```

**Output:**

```
for
Geeks

```

**示例 3:** 演示 listIterator(int index)抛出的*indexout of boundsexception*。

```
// Java code to illustrate IndexOutOfBoundsException
// thrown by listIterator(int index)

import java.util.Vector;
import java.util.ListIterator;

public class GFG {
    public static void main(String[] args)
    {
        // Declare empty vector
        Vector<String> vt
            = new Vector<String>();

        vt.add("Geeks");
        vt.add("for");
        vt.add("Geeks");

        // Declare list iterator at starting
        // index greater than vector size
        try {
            ListIterator listItr
                = vt.listIterator(5);
        }
        catch (IndexOutOfBoundsException e) {
            // Exception handling
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.lang.IndexOutOfBoundsException: Index: 5

```

**示例 4:** 演示当向量对象在创建列表迭代器后被修改时，列表迭代器对象抛出的*ConcurrentModificationException*。

```
// Java code to illustrate ConcurrentModificationException
// thrown by ListIterator object

import java.util.ConcurrentModificationException;
import java.util.Vector;
import java.util.ListIterator;

public class GFG {
    public static void main(String[] args)
    {
        // Declare empty vector
        Vector<String> vt = new Vector<String>();

        vt.add("Geeks");
        vt.add("for");

        // Declare list iterator
        ListIterator listItr = vt.listIterator();

        // modify vector after creating list iterator
        vt.add("Geeks");

        try {
            // Exception thrown here
            System.out.println(listItr.next());
        }
        catch (ConcurrentModificationException e) {
            // Exception handling
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Exception: java.util.ConcurrentModificationException

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/vector . html # listIterator–](https://docs.oracle.com/javase/8/docs/api/java/util/Vector.html#listIterator--)

</center>

</center>