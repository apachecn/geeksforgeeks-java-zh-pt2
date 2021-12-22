# Java 中的 OffsetTime query()方法，带示例

> 原文:[https://www . geeksforgeeks . org/offsettime-query-method-in-Java-with-examples/](https://www.geeksforgeeks.org/offsettime-query-method-in-java-with-examples/)

Java 中 OffsetTime 类的 **Query()** 方法这次使用指定的查询进行查询。

**语法:**

```java
public  R query(TemporalQuery query)
```

**参数:**该方法接受单个参数**查询**，指定要调用的查询，不为空。

**返回值:**返回查询结果，可能返回 null(由查询定义)。

**错误和异常:**函数抛出两个异常，描述如下:

*   **DateTimeException:** 无法查询则抛出。
*   **算术异常:**如果出现数值溢出，则抛出。

以下程序说明查询()方法:

**程序 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the query() method

import java.time.OffsetTime;
import java.time.temporal.TemporalQueries;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("14:25:10+11:00");

        System.out.printf("OffsetTime precision is %s%n",
                          time.query(TemporalQueries.precision()));
    }
}
```

**Output:** 

```java
OffsetTime precision is Nanos
```

**程序 2 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the query() method

import java.time.OffsetTime;
import java.time.temporal.TemporalQueries;

public class GFG {
    public static void main(String[] args)
    {

        // Parses the time
        OffsetTime time = OffsetTime.parse("11:15:20+11:05");

        System.out.printf("OffsetTime precision is %s%n",
                          time.query(TemporalQueries.precision()));
    }
}
```

**Output:** 

```java
OffsetTime precision is Nanos
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/offsettimee . html # query-Java . time . temporal query-](https://docs.oracle.com/javase/8/docs/api/java/time/OffsetTime.html#query-java.time.temporal.TemporalQuery-)T4】