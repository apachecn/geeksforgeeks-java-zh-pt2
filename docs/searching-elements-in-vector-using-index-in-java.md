# 在 Java 中使用索引搜索向量中的元素

> 原文:[https://www . geesforgeks . org/search-elements-in-vector-use-index-in-Java/](https://www.geeksforgeeks.org/searching-elements-in-vector-using-index-in-java/)

[Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 实现了一个动态数组，这意味着它可以根据需要增长或收缩。像数组一样，它包含可以使用整数索引访问的组件。一个 [**向量的一个元素**](https://www.geeksforgeeks.org/java-util-vector-class-java/) 可以使用不同方法的索引进行搜索。假设元素不在向量中，那么方法将返回-1。

**方法 1:(使用** [(对象 o)](https://www.geeksforgeeks.org/vector-indexof-method-in-java/) **)**

**申报**

```
public int indexOf(Object o)
```

**语法:**

```
Vector.indexOf(Object element)
```

**参数:**该方法接受矢量类型的强制参数*元素*。它指定需要在矢量中检查其出现的元素

**返回值:**该方法返回向量中元素第一次出现的索引或位置。否则，如果向量中不存在元素，它将返回 **-1** 。返回值是整数类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Searching Elements in Vector Using Index in Java
import java.util.Vector;

public class GFG {

    public static void main(String args[])
    {
        // initialization Of Vector
        Vector<String> details = new Vector<>(10);

        // Adding Elements To The
        // Vector
        details.add("Geeks For Geeks");
        details.add("Welcome");
        details.add("Bob");
        details.add("Hello");
        details.add("Geeks For Geeks");

        // Searching The Index Of Element
        System.out.println(
            "The index of element Geeks For Geeks in Vector is: "
            + details.indexOf("Geeks For Geeks"));
        System.out.println(
            "The index of element 2100 in Vector is: "
            + details.indexOf(2100));
    }
}
```

**Output**

```
The index of element Geeks For Geeks in Vector is: 0
The index of element 2100 in Vector is: -1
```

**方法二:(使用**T2【最后一个索引(对象 o)T4】)

**申报**

```
public int lastIndexOf(Object o)
```

**语法:**

```
Vector.lastIndexOf(Object element)
```

**参数:**参数*元素*属于矢量类型。它指的是需要检查最后一次出现的元素。

**返回值:**该方法返回元素在向量中最后一次出现的位置。如果该元素不在向量中，则该方法返回-1。返回值是整数类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Searching Elements in Vector
// Using Index in Java
import java.util.Vector;

public class GFG {

    public static void main(String args[])
    {
        // initialization Of Vector
        Vector<String> details = new Vector<>(10);

        // Adding Elements To The
        // Vector
        details.add("Geeks For Geeks");
        details.add("Welcome");
        details.add("Bob");
        details.add("Hello");        
        details.add("Geeks For Geeks");

        // print an element using it's index
        System.out.println(
            "The index of element Geeks For Geeks in Vector is: "
            + details.lastIndexOf("Geeks For Geeks"));
    }
}
```

**Output**

```
The index of element Geeks For Geeks in Vector is: 4
```

**方法 3:(使用 indexOf(Object，int)方法)**

**申报**

```
public int indexOf(Object o, int Starting_Index)
```

**语法**

```
Vector.indexOf(Object, int)
```

**参数:**

*   **starting_index:** 是一个向前开始搜索元素的索引。
*   **o:** 是要搜索的元素。

**返回值:**该向量中对象(o)第一次出现的索引，从给定的 starting _ Index 开始搜索

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Searching Elements in Vector Using Index in Java
import java.util.Vector;

public class GFG {

    public static void main(String args[])
    {
        // initialization Of Vector
        Vector<String> details = new Vector<>(10);

        // Adding Elements To The
        // Vector
        details.add("Geeks For Geeks");
        details.add("Welcome");
        details.add("Bob");
        details.add("Hello");
        details.add("Bob");
        details.add("Geeks For Geeks");

        System.out.println(
            "The index of element Bob in Vector is: "
            + details.indexOf("Bob", 3));
    }
}
```

**Output**

```
The index of element Bob in Vector is: 4
```

**方法 4:(使用 lastIndexOf(Object，int)方法)**

**申报**

```
public int lastIndexOf(Object o, int Starting_Index)
```

**语法**

```
Vector.lastIndexOf(Object, int)
```

**参数:**

*   **starting_index:** 是一个开始向后搜索元素的索引。
*   **o:** 是一个需要搜索的元素。

**返回值:**该向量中指定元素最后一次出现的索引，从 Starting_Index 向后搜索。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Searching Elements in Vector Using Index in Java
import java.util.Vector;

public class GFG {

    public static void main(String args[])
    {
        // create a instance of vector
        Vector<String> details = new Vector<>(10);

        // Adding Elements To The
        // Vector
        details.add("Geeks For Geeks");
        details.add("Welcome");
        details.add("Bob");
        details.add("Hello");
        details.add("Bob");
        details.add("Geeks For Geeks");

        System.out.println(
            "The index of element Bob in Vector is: "
            + details.lastIndexOf("Bob", 4));
    }
}
```

**Output**

```
The index of element Bob in Vector is: 4
```