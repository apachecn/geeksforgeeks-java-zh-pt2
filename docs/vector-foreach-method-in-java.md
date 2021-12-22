# Java 中的 Vector forEach()方法

> 原文:[https://www . geesforgeks . org/vector-foreach-method-in-Java/](https://www.geeksforgeeks.org/vector-foreach-method-in-java/)

Vector 的 **forEach()** 方法用于对 Vector 的 Iterable 的每个元素执行给定的操作，直到该方法处理完所有元素或发生异常。

如果方法指定了迭代顺序，则按照迭代顺序执行操作。操作引发的异常被传递给调用方。

除非重写类指定了并发修改策略，否则该操作无法修改元素的基础源，因此我们可以说该方法的行为是未指定的。

[在 Java 中从集合中检索元素](https://www.geeksforgeeks.org/retrieving-elements-from-collection-for-each-iterator-listiterator-enumerationiterator/)。

**语法:**

```
public void forEach(Consumer<? super E> action)
```

**参数:**该方法取一个参数*动作*，代表每个元素要执行的动作。

**返回值:**这个方法不返回任何东西。

**异常:**如果指定的动作为空，该方法抛出*空指针异常*。

下面的程序说明了向量的 forEach()方法:

**示例 1:** 在包含字符串集合的 Vector 上演示 forEach()方法的程序。

```
// Java Program Demonstrate forEach()
// method of Vector

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // create an Vector which going to
        // contains a collection of Strings
        Vector<String> data = new Vector<String>();

        // Add String to Vector
        data.add("Saltlake");
        data.add("LakeTown");
        data.add("Kestopur");

        System.out.println("List of Strings data");
        // forEach method of Vector and
        // print data
        data.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```
List of Strings data
Saltlake
LakeTown
Kestopur

```

**示例 2:** 在包含对象集合的向量上演示 forEach()方法的程序。

```
// Java Program Demonstrate forEach()
// method of Vector

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // create an Vector which going to
        // contains a collection of objects
        Vector<DataClass> vector = new Vector<DataClass>();

        // Add objects to vector
        vector.add(new DataClass("Shape", "Square"));
        vector.add(new DataClass("Area", "2433Sqft"));
        vector.add(new DataClass("Radius", "25m"));

        // print result
        System.out.println("list of Objects:");

        // forEach method of Vector and
        // print Objects
        vector.forEach((n) -> print(n));
    }

    // printing object data
    public static void print(DataClass n)
    {
        System.out.println("****************");
        System.out.println("Object Details");
        System.out.println("key : " + n.key);
        System.out.println("value : " + n.value);
    }
}

// create a class
class DataClass {

    public String key;
    public String value;

    DataClass(String key, String value)
    {
        this.key = key;
        this.value = value;
    }
}
```

**输出:**

```
list of Objects:
****************
Object Details
key : Shape
value : Square
****************
Object Details
key : Area
value : 2433Sqft
****************
Object Details
key : Radius
value : 25m

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/vector . html # forEach(Java . util . function . consumer)](https://docs.oracle.com/javase/10/docs/api/java/util/Vector.html#forEach(java.util.function.Consumer))