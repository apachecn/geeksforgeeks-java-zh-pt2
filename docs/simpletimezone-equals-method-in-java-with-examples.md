# Java 中 SimpleTimeZone 等于()方法，示例

> 原文:[https://www . geesforgeks . org/simple time zone-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/simpletimezone-equals-method-in-java-with-examples/)

**SimpleTimeZone 类**的 **equals()** 方法用于比较两个 SimpleTimeZone 对象的相等性。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该函数接受单个参数**对象**，这是一个要与之比较的简单时区对象。

**返回值:**该方法返回两个值:

*   如果给定的对象与这个 SimpleTimeZone 对象相同，则为 true
*   如果给定的对象与此 SimpleTimeZone 对象不同，则为 false

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.date.equals()
import java.util.SimpleTimeZone;

public class GFG {

    public static void main(String[] args)
    {
        // create first simple time zone object
        SimpleTimeZone obj1
            = new SimpleTimeZone(520, "India");

        // create second simple time zone object
        SimpleTimeZone obj2
            = new SimpleTimeZone(780, "India");

        // compare two objects and print the result
        System.out.println("Result of comparison is : "
                           + obj1.equals(obj2));
    }
}
```

**Output:**

```java
Result of comparison is : false

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.date.equals()
import java.util.SimpleTimeZone;

public class GFG {

    public static void main(String[] args)
    {
        // create first simple time zone object
        SimpleTimeZone obj1
            = new SimpleTimeZone(520, "India");

        // create second simple time zone object
        SimpleTimeZone obj2
            = new SimpleTimeZone(520, "India");

        // compare two objects and print the result
        System.out.println("Result of comparison is : "
                           + obj1.equals(obj2));
    }
}
```

**Output:**

```java
Result of comparison is : true

```