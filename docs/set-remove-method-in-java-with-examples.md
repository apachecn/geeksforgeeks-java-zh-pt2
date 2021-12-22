# 用示例在 Java 中设置 remove()方法

> 原文:[https://www . geesforgeks . org/set-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/set-remove-method-in-java-with-examples/)

方法用于从集合中移除特定的元素。

**语法:**

```java
boolean remove(Object O)
```

**参数:**参数 *O* 属于该集合维护的元素类型，并指定要从集合中移除的元素。

**返回值:**如果集合中存在指定的元素，该方法返回真，否则返回假。

下面程序举例说明了 java.util.Set.remove(Object O)方法:

```java
// Java code to illustrate Set.remove() method

import java.util.*;

public class SetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<String> set = new HashSet<String>();

        // Use add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the Set
        System.out.println("Set: " + set);

        // Removing elements using remove() method
        set.remove("Geeks");
        set.remove("4");
        set.remove("Welcome");

        // Displaying the Set after removal
        System.out.println("Set after removing elements: "
                           + set);
    }
}
```

**输出:**

```java
Set: [4, Geeks, Welcome, To]
Set after removing elements: [To]

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # remove(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#remove(java.lang.Object))