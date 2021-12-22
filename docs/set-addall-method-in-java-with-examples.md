# 用示例在 Java 中设置 addAll()方法

> 原文:[https://www . geesforgeks . org/set-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/set-addall-method-in-java-with-examples/)

**Java . util . set . addall(Collection C)**方法用于将上述集合中的所有元素追加到现有集合中。元素是随机添加的，没有遵循任何特定的顺序。

**语法:**

```java
boolean addAll(Collection C)
```

**参数:**参数 *C* 是要添加到集合中的任何类型的集合。

**返回值:**如果该方法成功地将集合 *C* 的元素追加到该集合中，则该方法返回真，否则返回假。

下面的程序说明了 Java.util.Set.addAll()方法:

**程序 1 :** 追加一个树集合。

```java
// Java code to illustrate addAll()
import java.io.*;
import java.util.*;

public class TreeSetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<String> st1 = new TreeSet<String>();

        // Use add() method to add elements into the Set
        st1.add("Welcome");
        st1.add("To");
        st1.add("Geeks");
        st1.add("4");
        st1.add("Geeks");
        st1.add("TreeSet");

        // Displaying the Set
        System.out.println("Set: " + st1);

        // Creating another Set
        Set<String> st2 = new TreeSet<String>();

        // Use add() method to add elements into the Set
        st2.add("Hello");
        st2.add("World");

        // Using addAll() method to Append
        st1.addAll(st2);

        // Displaying the final Set
        System.out.println("Set: " + st1);
    }
}
```

**输出:**

```java
Set: [4, Geeks, To, TreeSet, Welcome]
Set: [4, Geeks, Hello, To, TreeSet, Welcome, World]

```

**程序 2 :** 追加数组列表。

```java
// Java code to illustrate addAll()
import java.io.*;
import java.util.*;

public class SetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<String> st1 = new TreeSet<String>();

        // Use add() method to add elements into the Set
        st1.add("Welcome");
        st1.add("To");
        st1.add("Geeks");
        st1.add("4");
        st1.add("Geeks");
        st1.add("Set");

        // Displaying the Set
        System.out.println("Initial Set: " + st1);

        // An array collection is created
        ArrayList<String> collect = new ArrayList<String>();
        collect.add("A");
        collect.add("Computer");
        collect.add("Portal");

        // Using addAll() method to Append
        st1.addAll(collect);

        // Displaying the final Set
        System.out.println("Final Set: " + st1);
    }
}
```

**输出:**

```java
Initial Set: [4, Geeks, Set, To, Welcome]
Final Set: [4, A, Computer, Geeks, Portal, Set, To, Welcome]

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # addAll(Java . util . collection)](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#addAll(java.util.Collection))