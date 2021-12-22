# Java 中的 StringJoiner setEmptyValue()方法

> 原文:[https://www . geesforgeks . org/string joiner-setemptyvalue-method-in-Java/](https://www.geeksforgeeks.org/stringjoiner-setemptyvalue-method-in-java/)

[字符串连接符](https://www.geeksforgeeks.org/java-util-stringjoiner-java8/)的**设置空值(CharSequence emptyValue)** 设置确定该字符串连接符的字符串表示时要使用的字符序列，并且还没有添加任何元素，即当它为空时。emptyValue 参数的副本就是为此目的而制作的。请注意，一旦调用了 add 方法，StringJoiner 就不再被认为是空的，即使添加的元素对应于空字符串。

**语法:**

```java
public StringJoiner setEmptyValue(CharSequence emptyValue)
```

**参数:**该方法接受一个强制参数**空值**，它是作为空字符串连接符的值返回的字符

**返回:**这个方法返回这个 StringJoiner 本身，所以调用可能是链式的

**异常:**当空值参数为空时，该方法抛出**空指针异常**

以下示例说明了 setEmptyValue()方法:

**例 1:**

```java
// Java program to demonstrate
// setEmptyValue() method of StringJoiner

import java.util.StringJoiner;

public class GFG {
    public static void main(String[] args)
    {

        // Create a StringJoiner
        StringJoiner str = new StringJoiner(" ");

        // Print the empty StringJoiner
        System.out.println("Initial StringJoiner: "
                           + str);

        // Add an emptyValue
        // using setEmptyValue() method
        str.setEmptyValue("StrigJoiner is empty");

        // Print the StringJoiner
        System.out.println("After setEmptyValue(): "
                           + str);

        // Add elements to StringJoiner
        str.add("Geeks");
        str.add("forGeeks");

        // Print the StringJoiner
        System.out.println("Final StringJoiner: "
                           + str);
    }
}
```

**Output:**

```java
Initial StringJoiner: 
After setEmptyValue(): StrigJoiner is empty
Final StringJoiner: Geeks forGeeks

```

**示例 2:** 演示空指针异常

```java
// Java program to demonstrate
// setEmptyValue() method of StringJoiner

import java.util.StringJoiner;

public class GFG {
    public static void main(String[] args)
    {

        // Create a StringJoiner
        StringJoiner str = new StringJoiner(" ");

        // Print the empty StringJoiner
        System.out.println("Initial StringJoiner: "
                           + str);

        try {
            // Add a null emptyValue
            // using setEmptyValue() method
            str.setEmptyValue(null);
        }
        catch (Exception e) {
            System.out.println("Exception when adding null"
                               + " in setEmptyValue(): " + e);
        }
    }
}
```

**Output:**

```java
Initial StringJoiner: 
Exception when adding null in setEmptyValue(): 
    java.lang.NullPointerException: 
    The empty value must not be null

```