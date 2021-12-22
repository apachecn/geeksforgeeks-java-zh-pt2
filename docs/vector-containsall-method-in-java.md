# 向量包含 Java 中的 All()方法

> 原文:[https://www . geesforgeks . org/vector-contains all-in-method-Java/](https://www.geeksforgeeks.org/vector-containsall-method-in-java/)

**Java . util . vector . contains all()**方法用于检查该 Vector 是否包含指定集合中的所有元素。所以基本上它是用来检查一个向量是否包含一组元素。

**语法:**

```
Vector.containsAll(Collection col)
```

**参数:**该方法接受一个强制参数 **col** ，该参数属于向量类型。这是需要检查其元素是否存在于向量中的集合。

**返回值:**如果集合*列*中的所有元素都存在于向量中，则该方法返回**真**，否则返回**假**。

**异常:**如果指定的集合为空，该方法将抛出**空指针异常**。

下面的程序说明了 Java.util.Vector.containsAll()方法:

**程序 1:**

```
// Java code to illustrate containsAll()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("4");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Creating another empty Vector
        Vector<String> colvec_tor = new Vector<String>();

        colvec_tor.add("Geeks");
        colvec_tor.add("4");
        colvec_tor.add("Geeks");

        System.out.println("Are all the contents equal? " + vec_tor.containsAll(colvec_tor));

        // Creating another empty Vector
        Vector<String> colvec_tor2 = new Vector<String>();

        colvec_tor2.add("Hello");
        colvec_tor2.add("Geeks");

        System.out.println("Are all the contents equal? " + vec_tor.containsAll(colvec_tor2));
    }
}
```

**Output:**

```
Vector: [Welcome, To, Geeks, 4, Geeks]
Are all the contents equal? true
Are all the contents equal? false

```

**程序 2:**

```
// Java code to illustrate contains()
import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements into the Vector
        vec_tor.add(10);
        vec_tor.add(15);
        vec_tor.add(30);
        vec_tor.add(20);
        vec_tor.add(5);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Displaying the Vector
        System.out.println("Vector: " + vec_tor);

        // Creating another empty Vector
        Vector<Integer> colvec_tor = new Vector<Integer>();

        colvec_tor.add(20);
        colvec_tor.add(25);
        colvec_tor.add(30);

        System.out.println("Are all the contents equal? " + vec_tor.containsAll(colvec_tor));

        // Creating another empty Vector
        Vector<Integer> colvec_tor2 = new Vector<Integer>();

        colvec_tor2.add(10);
        colvec_tor2.add(20);

        System.out.println("Are all the contents equal? " + vec_tor.containsAll(colvec_tor2));
    }
}
```

**Output:**

```
Vector: [10, 15, 30, 20, 5]
Vector: [10, 15, 30, 20, 5]
Are all the contents equal? false
Are all the contents equal? true

```