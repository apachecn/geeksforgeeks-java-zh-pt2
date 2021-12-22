# Java 中的年月解析(CharSequence)方法，示例

> 原文:[https://www . geesforgeks . org/year month-parser charsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/yearmonth-parsecharsequence-method-in-java-with-examples/)

**YearMonth** 类的 **parse(CharSequence)** 方法用于从作为参数传递的字符串(如“2018-12”)中获取 YearMonth 的实例。该字符串必须具有可转换为 YearMonth 对象的有效值。字符串的格式必须是 uu-mm。0000 到 9999 范围之外的年份月份必须以加号或减号作为前缀。

**语法:**

```java
public static YearMonth parse(CharSequence text)

```

**参数:**
这个方法只接受一个参数**文本**，代表要解析的文本，这个字符串的格式必须像 uu-MM 一样

**返回值:**
这个方法返回解析后的年月。

**异常:**该方法抛出以下异常:

*   **如果文本无法解析，则为 datetime exception–**。

下面的程序说明了解析(字符序列文本)方法:

**程序 1:**

```java
// Java program to demonstrate
// YearMonth.parse(CharSequence text) method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a YearMonth object
        // using parse(CharSequence text)
        YearMonth yearMonth = YearMonth.parse("2019-12");

        // print instance
        System.out.println("YearMonth Parsed:"
                           + yearMonth);
    }
}
```

**Output:**

```java
YearMonth Parsed:2019-12

```

**程序 2:**

```java
// Java program to demonstrate
// YearMonth.parse(CharSequence text) method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a YearMonth object
        // using parse(CharSequence text)
        YearMonth yearMonth = YearMonth.parse("2022-05");

        // print instance
        System.out.println("YearMonth Parsed:"
                           + yearMonth);
    }
}
```

**Output:**

```java
YearMonth Parsed:2022-05

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/year month . html # parse(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/time/YearMonth.html#parse(java.lang.CharSequence))