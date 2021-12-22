# Java 中的 StringBuilder 容量()，示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-capacity-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-capacity-in-java-with-examples/)

**StringBuilder 类**的**容量()**方法用于返回 StringBuilder 对象的当前容量。容量是**插入新字符可用的存储量。**
**语法:**

```java
public int capacity()
```

**返回值:**该方法返回 StringBuilder 类的**当前容量**。
以下程序演示了 StringBuilder 类的容量()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the capacity() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object,
        // default capacity will be 16
        StringBuilder str = new StringBuilder();

        // get default capacity
        int capacity = str.capacity();

        System.out.println("Default Capacity of StringBuilder = "
                           + capacity);

        // add the String to StringBuilder Object
        str.append("Geek");

        // get capacity
        capacity = str.capacity();

        // print the result
        System.out.println("StringBuilder = " + str);
        System.out.println("Current Capacity of StringBuilder = "
                           + capacity);
    }
}
```

**Output**

```java
Default Capacity of StringBuilder = 16
StringBuilder = Geek
Current Capacity of StringBuilder = 16

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the capacity() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuilder object
        // with a String passed as parameter
        StringBuilder
            str
            = new StringBuilder("WelcomeGeeks");

        // get capacity
        int capacity = str.capacity();

        // print the result
        System.out.println("StringBuilder = " + str);
        System.out.println("Capacity of StringBuilder = "
                           + capacity);
    }
}
```

**Output:** 

```java
StringBuilder = WelcomeGeeks
Capacity of StringBuilder = 28
```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # capacity()](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#capacity())