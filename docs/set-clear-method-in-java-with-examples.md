# 用示例在 Java 中设置 clear()方法

> 原文:[https://www . geesforgeks . org/set-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/set-clear-method-in-java-with-examples/)

方法用于从集合中移除所有元素。使用 clear()方法只会清除集合中的所有元素，而不会删除集合。换句话说，我们可以说 clear()方法仅用于清空现有的集合。

**语法:**

```
void clear()
```

**参数:**该方法不取任何参数

**返回值:**该方法不返回值。

下面程序举例说明了 Java.util.method.clear()方法:

```
// Java code to illustrate clear()
import java.io.*;
import java.util.*;

public class SetDemo {
    public static void main(String args[])
    {
        // Creating an empty Set
        Set<String> st = new HashSet<String>();

        // Use add() method to add elements into the Set
        st.add("Welcome");
        st.add("To");
        st.add("Geeks");
        st.add("4");
        st.add("Geeks");

        // Displaying the Set
        System.out.println("Initial Set: " + st);

        // Clearing the Set using clear() method
        st.clear();

        // Displaying the final Set after clearing;
        System.out.println("The final set: " + st);
    }
}
```

**输出:**

```
Initial Set: [4, Geeks, Welcome, To]
The final set: []

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/set . html # clear()](https://docs.oracle.com/javase/7/docs/api/java/util/Set.html#clear())