# Java 中的 SortedSet isEmpty()方法，带示例

> 原文:[https://www . geesforgeks . org/sorted set-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-isempty-method-in-java-with-examples/)

**[java.util.SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 。isEmpty()** 方法用于检查 SortedSet 是否为空。如果排序集为空，则返回真，否则返回假。

**语法:**

```java
boolean isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果 SortedSet 为空，则该方法返回真，否则返回假。

**注**:在 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 中的 isEmpty()方法是从 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)继承而来的。

下面的程序说明了 java.util.SortedSet.isEmpty()方法:

```java
// Java code to illustrate isEmpty()

import java.io.*;
import java.util.*;

public class SortedSetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        SortedSet<String> set
            = new TreeSet<String>();

        // Use add() method to
        // add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the Set
        System.out.println("Set: " + set);

        // Check for the empty set
        System.out.println("Is the set empty? "
                           + set.isEmpty());

        // Clearing the set using clear() method
        set.clear();

        // Again Checking for the empty set
        System.out.println("Is the set empty? "
                           + set.isEmpty());
    }
}
```

**输出:**

```java
Set: [4, Geeks, To, Welcome]
Is the set empty? false
Is the set empty? true

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # isEmpty()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#isEmpty())