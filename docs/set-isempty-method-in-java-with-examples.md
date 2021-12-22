# 用示例在 Java 中设置 isEmpty()方法

> 原文:[https://www . geesforgeks . org/set-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/set-isempty-method-in-java-with-examples/)

java.util.Set.isEmpty()方法用于检查集合是否为空。如果集合为空，则返回真，否则返回假。

**语法:**

```java
boolean isEmpty()
```

**参数:**该方法不取任何参数

**返回值:**如果集合为空，方法返回真，否则返回假。

下面的程序说明了 java.util.Set.isEmpty()方法:

```java
// Java code to illustrate isEmpty()
import java.io.*;
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

        // Check for the empty set
        System.out.println("Is the set empty? " + set.isEmpty());

        // Clearing the set using clear() method
        set.clear();

        // Again Checking for the empty set
        System.out.println("Is the set empty? " + set.isEmpty());
    }
}
```

**输出:**

```java
Set: [4, Geeks, Welcome, To]
Is the set empty? false
Is the set empty? true

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # isEmpty()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#isEmpty())