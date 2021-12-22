# Java 12 的新特性

> 原文:[https://www.geeksforgeeks.org/new-features-of-java-12/](https://www.geeksforgeeks.org/new-features-of-java-12/)

甲骨文于 2019 年 3 月 19 日发布了 Java SE(标准版)12，之后他们计划每六个月发布一次新版本。JDK 12 比 JDK 11 有很多改进。这个最新版本提供了一系列新功能，如开关表达式、默认光盘档案、Shenandoah、微基准套件等。这些新功能将在下面讨论。

**1。** **开关表达式的变化**:

**开关表达式**现在将用作语句和表达式。这使得开关的代码简化和模式匹配成为可能。

*   In earlier versions, the absence of the break statement would lead to error-prone default failure.
*   **Default** is mandatory in the switch expression.

现在，交换机的新箭头语法介绍如下

```
case X -> {} 

```

表示只有当标签匹配时，才会执行箭头右侧的语句。

Java 11 和 Java 12 的 Switch 表达式可以比较如下:

**Java 11**T4

## Java

T7

```
// Java program to demonstrate the
// classic switch statement

import java.io.*;

class Java11switchStatement {

    static int getMealNumber(String meal)
    {
        // stores mealNumber
        int mealNumber;

        // classic switch statement
        switch (meal) {

        case "SOUP":
            mealNumber = 1;
            break;

        case "BURGER":

        case "CHIPS":

        case "SANDWICH":
            mealNumber = 2;
            break;

        case "SPAGETTI":

        case "MACRONI":
            mealNumber = 3;
            break;

        default:
            throw new IllegalStateException(
                "Cannot prepare " + meal);
        }

        return mealNumber;
    }
    public static void main(String[] args)
    {

        // define meal
        String meal = "BURGER";

        // print mealNumber
        System.out.println("The mealNumber is : "
                           + getMealNumber(meal));
    }
}
```

T8T10**输出**T1

**Java 12**

## Java

```
// Java program to demonstrate the
// new switch expression

import java.io.*;

class Java11switchStatement {

      // returns mealNumber
    static int getMealNumber(String meal)
    {

        // stores mealNumber using
        // new switch expression
        int mealNumber = switch (meal)
        {

           case "SOUP" -> 1;

           case "BURGER", "CHIPS", "SANDWICH" -> 2;

           case "SPAGETTI", "MACRONI" -> 3;

           default -> throw new IllegalException("");
        }

        return mealNumber;
    }

    public static void main(String[] args)
    {

        // define meal
        String meal = "BURGER";

        // print mealNumber
        System.out.println("The mealNumber is : "
                           + getMealNumber(meal));
    }
}
```

**输出**

```
The mealNumber is : 2

```

**2。** **谢南多亚(全新改良的垃圾收集器)**

这是一个实验特性，引入了一个新的垃圾收集(GC)算法，Shenandoah。它通过与运行的 Java 线程并发执行疏散工作来提供低暂停时间。因此，暂停时间与堆大小无关。例如，5MB 堆的暂停时间与 10GB 堆相同。

**3。** **JVM 常量 API** :这个 API 帮助那些操纵类和方法的程序。这些程序需要对字节代码指令进行建模，并处理可加载的常量。字符串或整数类型的常量也可以。然而，使用常量类型作为类变得很棘手。如果类不可访问或不存在，加载类可能会失败。有了新的应用编程接口，类描述符、方法类型描述符、方法句柄描述符和动态实例描述符等接口可以象征性地处理常量值，从而消除复杂性。

**4。****G1**可移植混合收集:默认垃圾收集器“垃圾优先”(G1)使用分析引擎来确定收集集，一旦收集开始，所有活动对象都应被收集而不会停止。这会导致超过目标暂停时间。为了解决这个问题，G1 收集组被分成可选部分和强制部分。通过对强制设置进行优先级排序，可以经常实现暂停时间目标。

**5。默认的 CDS 归档文件**:创建了一个类数据共享(CDS)归档文件，以使 JDK 构建过程更加高效，从而提高开箱即用的启动时间。

**6。** **微基准测试套件**:通过添加到 JDK 源代码的微基准测试套件，开发人员可以轻松运行现有的或新的基准测试。

**7。迅速从 G1 返回未使用的提交内存**:通过这个改进的特性，当 G1 空闲时，垃圾收集器会自动将未使用的堆内存返回给操作系统。这是通过 G1 对 Java 堆的并发检查来完成的。

**8)** **Files.mismatch()方法**:这个新方法比较两个文件。

*方法签名*

```
public static long mismatch(Path path1, Path path2) throws IOException

```

*返回:* **-1L** 如果没有不匹配其他**第一个不匹配**的位置 **。**

它返回两种情况下不匹配的位置。

*   **Case 1** : If the file sizes do not match. Here, the size of the smaller file is returned.
*   **Case 2** : If the bytes do not match. Here, the first unmatched byte is returned.

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;

public class FilesCompareExample {

    public static void main(String[] args)
        throws IOException
    {
        Path path1 = Files.createTempFile("file1", ".txt");
        Path path2 = Files.createTempFile("file2", ".txt");
        Files.writeString(path1, "Geeks for geeks");
        Files.writeString(path2, "Geeks for geeks");

        long mismatch1 = Files.mismatch(path1, path2);

        System.out.println(
            "File Mismatch position or -1 is returned if there is no mismatch");

        System.out.println(
            "Mismatch position in file1 and file2 is : "
            + mismatch1);

        path1.toFile().deleteOnExit();
        path2.toFile().deleteOnExit();

        System.out.println();

        Path path3 = Files.createTempFile("file3", ".txt");
        Path path4 = Files.createTempFile("file4", ".txt");
        Files.writeString(path3, "Geeks for geeks");
        Files.writeString(path4, "Geeks for the geeks");

        long mismatch2 = Files.mismatch(path3, path4);

        System.out.println(
            "Mismatch position in file3 and file4 is : "
            + mismatch2);

        path3.toFile().deleteOnExit();
        path4.toFile().deleteOnExit();
    }
}
```

**输出**

```
Mismatch position in file1 and file2 is : -1 
Mismatch position in file3 and file4 is : 10 

```

**9)紧凑数字格式**:由于空间限制，这是应用于通用数字(如十进制、货币、百分比)的格式，使其紧凑。在下面的示例中，1000 将被格式化为短样式的“1K”和长样式的“1000”。

## 爪哇

```
import java.text.NumberFormat;
import java.util.Locale;

public class CompactFormatExample {
    public static void main(String[] args)
    {
        NumberFormat fmtLong
            = NumberFormat.getCompactNumberInstance(
                Locale.US, NumberFormat.Style.LONG);

        System.out.println(fmtLong.format(100));
        System.out.println(fmtLong.format(1000));
        System.out.println(fmtLong.format(10000));

        NumberFormat fmtShort
            = NumberFormat.getCompactNumberInstance(
                Locale.US, NumberFormat.Style.SHORT);

        System.out.println(fmtShort.format(100));
        System.out.println(fmtShort.format(1000));
        System.out.println(fmtShort.format(10000));
    }
}
```

**输出**

```
100
1 thousand
10 thousand
100
1K
10K

```

**10)**Stream API 中的**teeting Collectors****:Collectors . teeting()是新的辅助函数，有助于将两步函数执行到一步中。这导致代码不太冗长。**

*方法签名*

```
public static Collector teeing​ (Collector downstream1, Collector downstream2, BiFunction merger);

```

这里，我们在两个不同的收集器上执行两个不同的流操作，结果使用提供的**双功能**进行合并。

**例:**

## 爪哇

```
import java.io.*;
import java.util.*;

class TeeingCollectorsExample {
    public static void main(String[] args)
    {
        double mean
            = Stream.of(2, 3, 4, 5, 6)
                  .collect(Collectors.teeing(
                      summingDouble(i -> i), counting(),
                      (sum, n) -> sum / n));

        System.out.println(mean);
    }
}
```

**输出**

```
4.0

```

**11)** **Java String 新方法** : Java 12 在 String 类中引入了以下新方法:

**i)** **缩进(int n)** :它根据传递的参数调整给定字符串每行的缩进。

根据通过的 **n** 的值，我们可以有以下情况:

*   If **n > 0** , insert a space at the beginning of each line.
*   If **n < 0** , delete the space at the beginning of each line.
*   If **n < 0** and **n < have available spaces** , delete all leading spaces [T13

**输出**

```
**********
  Welcome
  Good Morning
**********
   **********
     Welcome
     Good Morning
   **********
**********
Welcome
Good Morning
********** 

```

**二)变换(功能<？超级字符串，？扩展 R > f)** :用于调用一个需要字符串参数的函数，产生结果 R

```
String s = "Java,Python,Angular";
List result = s.transform(s1 -> {return Arrays.asList(s1.split(","));});
System.out.println(result);

```

**输出**

```
[Java, Python, Angular]

```

**iii)可选的<字符串> describeConstable()** :该方法将返回一个可选的对象，该对象包含字符串实例的描述符。

```
String message = "Welcome!";
Optional<String> opOfMessage = message.describeConstable();
System.out.println(opOfMessage);

```

**输出**

```
Optional[Welcome!]

```

**iv)字符串解析标准描述(方法句柄。查找查找)**:这个方法将返回一个[字符串](https://www.geeksforgeeks.org/string-class-in-java/)对象，它是调用字符串实例的描述符。

```
String message = "Welcome!";
String constantDesc = message.resolveConstantDesc(MethodHandles.lookup());
System.out.println(constantDesc);

```

**输出**

```
Welcome!

```

尽管与 Java 8 相比，Java 12 还没有获得普及，但是新特性的增加更加频繁，使得 Java 可以与其他语言的更好特性相媲美，从而保持了它在市场上的普及。