# Java 中的 Vector removeAll()方法

> 原文:[https://www . geesforgeks . org/vector-remove all-method-in-Java/](https://www.geeksforgeeks.org/vector-removeall-method-in-java/)

**T1。移除所有(集合列)**方法用于从向量中移除指定集合中存在的所有元素。

**语法:**

```
Vector.removeAll(Collection col)
```

**参数:**该方法接受一个强制参数**列**，它是要从向量中移除其元素的集合。

**返回值:**这个方法返回**真**如果向量由于操作而改变，否则**假**。

**异常:**如果指定的集合为空，该方法将抛出**空指针异常**。

下面的程序说明了方法:

**程序 1:**

```
// Java code to illustrate removeAll()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements in the Vector
        vec_tor.add("Geeks");
        vec_tor.add("for");
        vec_tor.add("Geeks");
        vec_tor.add("10");
        vec_tor.add("20");

        // Output the Vector
        System.out.println("Vector: " + vec_tor);

        // Creating an empty Vector
        Vector<String> colvec_tor = new Vector<String>();

        // Use add() method to add elements in the Vector
        colvec_tor.add("Geeks");
        colvec_tor.add("for");
        colvec_tor.add("Geeks");

        // Remove the head using remove()
        boolean changed = vec_tor.removeAll(colvec_tor);

        // Print the result
        if (changed)
            System.out.println("Collection removed");
        else
            System.out.println("Collection not removed");

        // Print the final Vector
        System.out.println("Final Vector: " + vec_tor);
    }
}
```

**Output:**

```
Vector: [Geeks, for, Geeks, 10, 20]
Collection removed
Final Vector: [10, 20]

```

**程序 2:**

```
// Java code to illustrate removeAll()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {

        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements in the Vector
        vec_tor.add(1);
        vec_tor.add(2);
        vec_tor.add(3);
        vec_tor.add(10);
        vec_tor.add(20);

        // Output the Vector
        System.out.println("Vector: " + vec_tor);

        // Creating an empty Vector
        Vector<Integer> colvec_tor = new Vector<Integer>();

        // Use add() method to add elements in the Vector
        colvec_tor.add(30);
        colvec_tor.add(40);
        colvec_tor.add(50);

        // Remove the head using remove()
        boolean changed = vec_tor.removeAll(colvec_tor);

        // Print the result
        if (changed)
            System.out.println("Collection removed");
        else
            System.out.println("Collection not removed");

        // Print the final Vector
        System.out.println("Final Vector: " + vec_tor);
    }
}
```

**Output:**

```
Vector: [1, 2, 3, 10, 20]
Collection not removed
Final Vector: [1, 2, 3, 10, 20]

```