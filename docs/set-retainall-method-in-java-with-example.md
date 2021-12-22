# 用示例

在 Java 中设置 retainAll()方法

> 原文:[https://www . geesforgeks . org/set-retain all-method-in-Java-with-example/](https://www.geeksforgeeks.org/set-retainall-method-in-java-with-example/)

**java.util.Set** 接口的**retainnal()**方法用于从该集合中保留指定集合中包含的所有元素。

**语法:**

```java
public boolean retainAll(Collection c)
```

**参数:**该方法以**集合 c** 为参数，包含从该集合中保留的元素。

**返回值:**如果该设置因调用而改变，则该方法返回**真**。

**异常:**如果该集合包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则该方法抛出**空指针异常**。

以下是说明*retainal()*方法的例子。

**例 1:**

```java
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of Set
            Set<Integer> arrset1 = new HashSet<Integer>();

            // Populating arrset1
            arrset1.add(1);
            arrset1.add(2);
            arrset1.add(3);
            arrset1.add(4);
            arrset1.add(5);

            // print arrset1
            System.out.println("Set before retainAll() operation : "
                               + arrset1);

            // Creating another object of  Set
            Set<Integer> arrset2 = new HashSet<Integer>();
            arrset2.add(1);
            arrset2.add(2);
            arrset2.add(3);

            // print arrset2
            System.out.println("Collection Elements to be retained : "
                               + arrset2);

            // Removing elements from arrset
            // specified in arrset2
            // using retainAll() method
            arrset1.retainAll(arrset2);

            // print arrset1
            System.out.println("Set after retainAll() operation : "
                               + arrset1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Set before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : [1, 2, 3]
Set after retainAll() operation : [1, 2, 3]

```

**例 2:** 为*零点异常*。

```java
// Java program to demonstrate
// retainAll() method for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // Creating object of Set<Integer>
            Set<Integer> arrset1 = new HashSet<Integer>();

            // Populating arrset1
            arrset1.add(1);
            arrset1.add(2);
            arrset1.add(3);
            arrset1.add(4);
            arrset1.add(5);

            // print arrset1
            System.out.println("Set before retainAll() operation : "
                               + arrset1);

            // Creating another object of Set<Integer>
            Set<Integer> arrset2 = null;

            // print arrset2
            System.out.println("Collection Elements to be retained : "
                               + arrset2);

            System.out.println("\nTrying to pass "
                               + "null as a specified element\n");

            // Removing elements from arrset
            // specified in arrset2
            // using retainAll() method
            arrset1.retainAll(arrset2);

            // print arrset1
            System.out.println("Set after retainAll() operation : "
                               + arrset1);
        }

        catch (NullPointerException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
Set before retainAll() operation : [1, 2, 3, 4, 5]
Collection Elements to be retained : null

Trying to pass null as a specified element

Exception thrown : java.lang.NullPointerException

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # retailnall(Java . util . collection)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#retainAll(java.util.Collection))