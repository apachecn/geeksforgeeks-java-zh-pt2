# Java 中的年解析(CharSequence)方法，示例

> 原文:[https://www . geesforgeks . org/year-parser charsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/year-parsecharsequence-method-in-java-with-examples/)

**Year** 类的 **parse(CharSequence)** 方法用于从作为参数传递的字符串(如“2018”)中获取 Year 的实例。该字符串必须具有可转换为年份的有效值。0000 到 9999 范围之外的年份必须以加号或减号作为前缀。

**语法:**

```java
public static Year parse(CharSequence text)

```

**参数:**该方法只接受一个参数**文本**，代表要解析的文本，如“2021”。

**返回值:**该方法返回解析后的年份。

**异常:**该方法抛出以下异常:

*   **日期时间异常:**如果文本无法解析。

下面的程序说明了解析(字符序列文本)方法:

**程序 1:**

```java
// Java program to demonstrate
// Year.parse(CharSequence text) method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        // using parse(CharSequence text)
        Year year = Year.parse("2019");

        // print instance
        System.out.println("Year Parsed:"
                           + year);
    }
}
```

**Output:**

```java
Year Parsed:2019

```

**程序 2:**

```java
// Java program to demonstrate
// Year.parse(CharSequence text) method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a Year object
        // using parse(CharSequence text)
        Year year = Year.parse("2018");

        // print instance
        System.out.println("Year Parsed:"
                           + year);
    }
}
```

**Output:**

```java
Year Parsed:2018

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year . html # parse(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/time/Year.html#parse(java.lang.CharSequence))