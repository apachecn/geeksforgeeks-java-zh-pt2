# Java 中的 NumberFormat 类

> 原文:[https://www.geeksforgeeks.org/numberformat-class-java/](https://www.geeksforgeeks.org/numberformat-class-java/)

**NumberFormat** 是所有数字格式的抽象基类。这个类提供了格式化和解析数字的接口。NumberFormat 还提供了确定哪些[地区](https://docs.oracle.com/javase/7/docs/api/java/util/Locale.html)(美国、印度、意大利等)有数字格式以及它们的名称的方法。NumberFormat 帮助您格式化和解析任何地区的数字。

**例:**假设我们有一个双数型数。但是这个双数在不同的国家有不同的表现方式。要根据不同的国家表示一个数字，我们必须借助 NumberFormat 类，如:

```
double d = 123456.789;
For India, it is represented like 1,23,456.789
For US, it is represented like 123,456.789
For ITALY, it is represented like 123.456,789

```

**number format 类的一些要点:**

*   NumberFormat class exists in java.text package and is an abstract class.
*   The number class realizes serializability and cloning.
*   NumberFormat is a direct subclass of the Format class.
*   Number formats are generally out of sync. It is recommended to create a separate format instance for each thread. If multiple threads access a format at the same time, it must be synchronized externally.

**number format 类中存在的方法:**

*   **public static numberformat getinstance ();** : Get the NumberFormat object of the default locale.
*   **public static numberformat get currency instance ();** : Get the numeric format object of the default locale, expressed in a specific currency.
*   **菲公 number 格式 getpercentinstance**:
*   **public static numberformat getinstance (locale l);** : Get the NumberFormat object of the specified area object.
*   **Public static format (length l);** : Convert java number to locale object.

```
// Java Program to illustrate NumberFormat class use
import java.util.*;
import java.text.*;
class NumberFormatDemo {
  public static void main(String[] args) {
    double d = 123456.789;
    NumberFormat nf = NumberFormat.getInstance(Locale.ITALY);
    System.out.println("ITALY representation of " + d + " : "
                                           + nf.format(d));
  }
}
```

输出:

```
ITALY representation of 123456.789 : 123.456, 789

```