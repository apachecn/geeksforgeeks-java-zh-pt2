# Java 中的 Vector removeAllElements()方法，示例

> 原文:[https://www . geesforgeks . org/vector-remove alliances-method-in-Java-with-example/](https://www.geeksforgeeks.org/vector-removeallelements-method-in-java-with-example/)

**Java . util . Vector . remove Allealements()**方法用于移除该向量中的所有组件，并将其大小设置为零。

**语法:**

```
Vector.removeAllElements()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回值。

下面的程序说明了 Java . util . vector . remove alloyments()方法。

**例 1:**

```
// Java code to illustrate removeAllElements()
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vector = new Vector<String>();

        // Use add() method to add elements into the Vector
        vector.add("Welcome");
        vector.add("To");
        vector.add("Geeks");
        vector.add("4");
        vector.add("Geeks");

        // Displaying the Vector
        System.out.println("Vector: " + vector);

        // removeAllElementsing the Vector
        // using removeAllElements() method
        vector.removeAllElements();

        // Displaying the final Vector after removeAllElement
        System.out.println("The final Vector: " + vector);
    }
}
```

**Output:**

```
Vector: [Welcome, To, Geeks, 4, Geeks]
The final Vector: []

```

**例 2:**

```
// Java code to illustrate removeAllElements()
import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vector = new Vector<Integer>();

        // Use add() method to add elements into the Queue
        vector.add(10);
        vector.add(15);
        vector.add(30);
        vector.add(20);
        vector.add(5);

        // Displaying the Vector
        System.out.println("Vector: " + vector);

        // removeAllElementsing the Vector
        // using removeAllElements() method
        vector.removeAllElements();

        // Displaying the final Vector after removeAllElement
        System.out.println("The final Vector: " + vector);
    }
}
```

**Output:**

```
Vector: [10, 15, 30, 20, 5]
The final Vector: []

```