# Java 中的 SortedSet add()方法，示例

> 原文:[https://www . geesforgeks . org/sorted set-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-add-method-in-java-with-examples/)

Java 中 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 的 **add()** 方法用于将特定元素添加到 [Set](https://www.geeksforgeeks.org/set-in-java/) 集合中。只有当集合中没有指定的元素时，函数才会添加元素，否则，如果集合中已经有元素，函数将返回 False。

**语法:**

```java
boolean add(E element)

Where E is the type of element maintained
by this Set collection.

```

**参数:**参数*元素*属于此集合维护的元素类型，它是指要添加到集合中的元素。

**返回值:**如果元素不在集合中并且是新的，函数返回真，否则如果元素已经在集合中，函数返回假。

**注**:这个 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 的方法继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

下面的程序说明了 Java.util.Set.add()方法的使用:

**程序 1** :

```java
// Java code to illustrate add() method

import java.io.*;
import java.util.*;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        SortedSet<String> s
            = new TreeSet<String>();

        // Use add() method
        // to add elements into the Set
        s.add("Welcome");
        s.add("To");
        s.add("Geeks");
        s.add("4");
        s.add("Geeks");
        s.add("Set");

        // Displaying the Set
        System.out.println("Set: " + s);
    }
}
```

**输出:**

```java
Set: [4, Geeks, Set, To, Welcome]

```

**程序二** :

```java
// Java code to illustrate add() method

import java.io.*;
import java.util.*;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        SortedSet<Integer> s
            = new TreeSet<Integer>();

        // Use add() method
        // to add elements into the Set
        s.add(10);
        s.add(20);
        s.add(30);
        s.add(40);
        s.add(50);
        s.add(60);

        // Displaying the Set
        System.out.println("Set: " + s);
    }
}
```

**输出:**

```java
Set: [10, 20, 30, 40, 50, 60]

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # add(E)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#add(E))