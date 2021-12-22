# Java 中 Period 等于()的方法，示例

> 原文:[https://www . geesforgeks . org/period-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-equals-method-in-java-with-examples/)

Java 中 Period 类的 equals()方法用于检查两个给定的周期是否相等。

比较基于类型“期间”以及三年、三个月和三个日期中的每一个。要相等，三年、月和日期必须各自相等。

**语法:**

```java
public boolean equals(Period secondPeriod)
```

**参数:**该方法接受单个参数*秒周期*，这是另一个比较周期。

**返回值:**如果给定周期相等，上述方法返回真，否则返回假。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java code to show the period
// equals for two given periods
import java.time.LocalDate;
import java.time.Period;

public class PeriodClass {

    // Function to check if two given periods
    // are equals or not
    static boolean checkIfEqualPeriod(Period firstPeriod,
                                      Period secondPeriod)
    {

        return firstPeriod.equals(secondPeriod);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Given period
        Period first = Period.ofDays(28);
        Period second = Period.ofDays(8);

        System.out.println(checkIfEqualPeriod(first, second));
    }
}
```

**输出:**

```java
false

```

**程序二:**

```java
// Java code to show the period
// equals for two given periods
import java.time.LocalDate;
import java.time.Period;

public class PeriodClass {

    // Function to check if two given periods
    // are equals or not
    static boolean checkIfEqualPeriod(Period firstPeriod,
                                      Period secondPeriod)
    {

        return firstPeriod.equals(secondPeriod);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Given period
        Period first2 = Period.ofDays(28);
        Period second2 = Period.ofDays(28);

        System.out.println(checkIfEqualPeriod(first2, second2));
    }
}
```

**输出:**

```java
true

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/period . html # equals-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/time/Period.html#equals-java.lang.Object-)