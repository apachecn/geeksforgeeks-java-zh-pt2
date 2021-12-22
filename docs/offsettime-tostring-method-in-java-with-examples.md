# Java 中的 OffsetTime toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-tostring-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **toString()** 方法将该日期输出为字符串，例如“11:25:10+11:10”。

**语法:**

```java
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**返回该日期的字符串表示形式，不为空。

下面的程序说明了 toString()方法:

```java
// Java program to demonstrate the toString() method

import java.time.OffsetTime;

public class GFG {
    public static void main(String[] args)
    {
        // Gets the current time
        OffsetTime time = OffsetTime.now();

        // Gets the local time
        System.out.println("Local-time in string format: " 
                                        + time.toString());
    }
}
```

**输出:**

```java
Local-time in string format: 04:04:24.595Z

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettime . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#toString--)