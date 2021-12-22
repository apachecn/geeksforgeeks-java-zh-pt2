# Java 中的 Vector toString()方法，示例

> 原文:[https://www . geesforgeks . org/vector-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/vector-tostring-method-in-java-with-example/)

[Java . util . Vector .](https://www.geeksforgeeks.org/java-util-vector-class-java/)toString()是 Vector 的一种内置方法，用于以字符串形式获取 Vector 对象的字符串表示，以“，”分隔条目。所以基本上 toString()方法是用来把 Vector 的所有元素转换成 String。
**语法:**

```
Vector.toString()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回由向量元素的字符串表示组成的字符串表示。
以下程序说明 java.util.Vector.toString()方法的工作:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the toString() method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // creating vector type object
        Vector<String> vector = new Vector<String>();

        // Inserting elements into the table
        vector.add("Geeks");
        vector.add("4");
        vector.add("Geeks");
        vector.add("Welcomes");
        vector.add("You");

        // Displaying the Vector
        System.out.println("Vector: " + vector);

        // Displaying the string representation
        System.out.println("The String representation is: "
                           + vector.toString());
    }
}
```

**Output:** 

```
Vector: [Geeks, 4, Geeks, Welcomes, You]
The String representation is: [Geeks, 4, Geeks, Welcomes, You]
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the toString() method
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Vector
        Vector<Integer> vector
            = new Vector<Integer>();

        // Inserting elements into the table
        vector.add(10);
        vector.add(15);
        vector.add(20);
        vector.add(25);
        vector.add(30);

        // Displaying the Vector
        System.out.println("Initial Vector is: " + vector);

        // Displaying the string representation
        System.out.println("The String representation is: "
                           + vector.toString());
    }
}
```

**Output:** 

```
Initial Vector is: [10, 15, 20, 25, 30]
The String representation is: [10, 15, 20, 25, 30]
```