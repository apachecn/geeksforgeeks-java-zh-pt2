# 用示例

在 Java 中设置 size()方法

> 原文:[https://www . geesforgeks . org/set-size-method-in-Java-with-example/](https://www.geeksforgeeks.org/set-size-method-in-java-with-example/)

java.util.Set.size()方法用于获取集合的大小或集合中存在的元素数量。

**语法:**

```java
int size()

```

**参数:**该方法不取任何参数。

**返回值:**该方法返回集合中元素的大小或数量。

下面的程序说明了 java.util.Set.size()方法:

```java
// Java code to illustrate Set.size() method

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

        // Displaying the size of the Set
        System.out.println("The size of the set is: " + set.size());
    }
}
```

**输出:**

```java
Set: [4, Geeks, Welcome, To]
The size of the set is: 4

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # size()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#size())