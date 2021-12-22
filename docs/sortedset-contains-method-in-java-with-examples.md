# SortedSet 包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/sorted set-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/sortedset-contains-method-in-java-with-examples/)

**包含()**方法用于检查特定元素是否存在于[排序集中](https://www.geeksforgeeks.org/sortedset-java-examples/)中。所以基本上它是用来检查一个 SortedSet 是否包含任何特定的元素。

**语法:**

```java
boolean contains(Object element)
```

**参数:**参数*元素*属于排序集类型。这是需要测试的元素，无论它是否存在于集合中。

**返回值:**如果元素存在于集合中，方法返回真，否则返回假。

**注**:在 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 中的 contains()方法是继承了 Java 中的 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)。

下面的程序说明了 Java.util.Set.contains()方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// SortedSet.contains() method

import java.io.*;
import java.util.*;

public class SortedSetDemo {
    public static void main(String args[])
    {

        // Creating an empty Set
        SortedSet<String> set
            = new TreeSet<String>();

        // Using add() method to
        // add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the Set
        System.out.println("Set: " + set);

        // Check for "Geeks" in the set
        System.out.println(
            "Does the Set contains 'Geeks'? "
            + set.contains("Geeks"));

        // Check for "4" in the set
        System.out.println(
            "Does the Set contains '4'? "
            + set.contains("4"));

        // Check if the Set contains "No"
        System.out.println(
            "Does the Set contains 'No'? "
            + set.contains("No"));
    }
}
```

**Output:** 

```java
Set: [4, Geeks, To, Welcome]
Does the Set contains 'Geeks'? true
Does the Set contains '4'? true
Does the Set contains 'No'? false
```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html #包含(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#contains(java.lang.Object))