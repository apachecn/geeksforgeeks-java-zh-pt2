# Java 中的 TimeUnit valueOf()方法，示例

> 原文:[https://www . geesforgeks . org/time unit-value of-method-in-Java-with-examples/](https://www.geeksforgeeks.org/timeunit-valueof-method-in-java-with-examples/)

**时间单位类**的 **valueOf()** 方法返回指定名称的该类型枚举常量。该字符串必须与用于声明此类型的枚举常量的标识符完全匹配。(不允许使用额外的空白字符。)

**语法:**

```
public static TimeUnit valueOf(String name)
```

**参数:**这个方法接受一个强制参数**名称**，这是要返回的枚举常量的名称。

**返回值:**该方法返回指定名称的**枚举常量**

**异常:**该方法抛出以下异常:

*   **IllegalArgumentException**–如果此枚举类型没有具有指定名称的常量
*   **空指针异常**–如果参数为空

下面的程序说明了 TimeUnit valueOf()方法的实现:

**程序 1:**

```
// Java program to demonstrate
// valueOf() method of TimeUnit Class

import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {

        // Create an object of TimeUnit class
        // using valueOf() method
        // Below statement is equivalent to
        // TimeUnit Days = TimeUnit.DAYS;
        TimeUnit Days = TimeUnit.valueOf("DAYS");

        // Print the Enum of TimeUnit Object
        System.out.println("TimeUnit object "
                           + "is of type: "
                           + Days);

        // Convert current object to Hours
        System.out.println("1 Day = "
                           + Days.toHours(1)
                           + " Hours");
    }
}
```

**Output:**

```
TimeUnit object is of type: DAYS
1 Day = 24 Hours

```

**程序 2:** 演示空指针异常

```
// Java program to demonstrate
// valueOf() method of TimeUnit Class

import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {

        try {

            System.out.println("Trying to create "
                               + "TimeUnit object "
                               + "using null Enum type");

            // Create an object of TimeUnit class
            // using valueOf() method
            // by passing null as parameter
            TimeUnit Days = TimeUnit.valueOf(null);
        }

        catch (NullPointerException e) {
            System.out.println("\nException thrown: " + e);
        }
    }
}
```

**Output:**

```
Trying to create TimeUnit object using null Enum type

Exception thrown: java.lang.NullPointerException: Name is null

```

**程序 3:** 演示 IllegalArgumentException

```
// Java program to demonstrate
// valueOf() method of TimeUnit Class

import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {

        try {

            System.out.println("Trying to create "
                               + "TimeUnit object "
                               + "using ABCD Enum type");

            // Create an object of TimeUnit class
            // using valueOf() method
            // by passing ABCD as parameter
            TimeUnit Days = TimeUnit.valueOf("ABCD");
        }

        catch (IllegalArgumentException e) {
            System.out.println("\nException thrown: " + e);
        }
    }
}
```

**Output:**

```
Trying to create TimeUnit object using ABCD Enum type

Exception thrown: java.lang.IllegalArgumentException: No enum constant java.util.concurrent.TimeUnit.ABCD

```