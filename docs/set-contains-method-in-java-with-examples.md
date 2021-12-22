# 集合包含 Java 中的()方法，示例

> 原文:[https://www . geesforgeks . org/set-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/set-contains-method-in-java-with-examples/)

方法用于检查集合中是否存在特定的元素。所以它基本上是用来检查一个集合是否包含任何特定的元素。

**语法:**

```
boolean contains(Object element)
```

**参数:**参数*元素*属于集合类型。这是需要测试的元素，无论它是否存在于集合中。

**返回值:**如果元素存在于集合中，方法返回真，否则返回假。

下面程序举例说明了

```
// Java code to illustrate Set.contains() method
import java.io.*;
import java.util.*;

public class HashSetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<String> set = new HashSet<String>();

        // Using add() method to add elements into the Set
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the Set
        System.out.println("Set: " + set);

        // Check for "Geeks" in the set
        System.out.println("Does the Set contains 'Geeks'? "
                           + set.contains("Geeks"));

        // Check for "4" in the set
        System.out.println("Does the Set contains '4'? "
                           + set.contains("4"));

        // Check if the Set contains "No"
        System.out.println("Does the Set contains 'No'? "
                           + set.contains("No"));
    }
}
```

**输出:**

```
Set: [4, Geeks, Welcome, To]
Does the Set contains 'Geeks'? true
Does the Set contains '4'? true
Does the Set contains 'No'? false

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html #包含(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#contains(java.lang.Object))