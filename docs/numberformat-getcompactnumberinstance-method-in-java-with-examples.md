# Java 中的 number format getCompactNumberInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/number format-getcompactnumberinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/numberformat-getcompactnumberinstance-method-in-java-with-examples/)

[NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 是所有数字格式的抽象基类。这个类提供了格式化和解析数字的接口。NumberFormat 类还提供了确定哪些地区(美国、意大利等)有数字格式及其名称的方法

NumberFormat 帮助您格式化和解析任何地区的数字。您的代码可以完全独立于小数点、千位分隔符甚至所使用的特定十进制数字的区域设置惯例，或者数字格式是否为偶数十进制。

**班级编号格式层次:**

```
java.lang.Object
    java.text.Format
        java.text.NumberFormat
```

**施工方:**

<figure class="table">

| 构造器 | 描述 |
| --- | --- |
| NumberFormat() | 唯一的建造者。(对于子类构造函数的调用，通常是隐式的。) |

</figure>

**语法**:

```
public abstract class NumberFormat extends Format
```

**getcompactnumberstance()方法:**

**注**:Java 12 中增加了 getCompactNumberInstance()方法。因此，请确保您的机器上安装了 Java 12 或更高版本。您可以通过以下方式检查 java 版本:

```
java -version
```

在 cmd 中键入上述命令并检查版本。应该在 Java 12 以上。

**输出**

```
java version "13.0.2" 2020-01-14
Java(TM) SE Runtime Environment (build 13.0.2+8)
Java HotSpot(TM) 64-Bit Server VM (build 13.0.2+8, mixed mode, sharing)
```

**注**:Java 12 中增加了这个方法。因此，请确保您的机器上安装了 Java 12 或更高版本。您可以通过轮询命令检查 java 版本，如下所示:

```
java -version
```

在 cmd 中键入上述命令并检查版本。应该在 Java 12 以上。

**输出:**

```
java version "13.0.2" 2020-01-14
Java(TM) SE Runtime Environment (build 13.0.2+8)
Java HotSpot(TM) 64-Bit Server VM (build 13.0.2+8, mixed mode, sharing)
```

> 这里的 Java 版本是 13.0.2。

**实施:**

**方法 1:**getcompactnumberstance()

它是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的内置方法，为默认 Format 区域设置返回一个具有“SHORT”格式样式的紧凑数字格式。

**语法:**

```
public static NumberFormat getCompactNumberInstance()
```

**参数:**此功能不接受任何参数。

**返回值:**用于压缩数字格式的数字格式实例。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implement NumberFormat class by
// Illustrating getCompactNumberInstance() Method 

// Importing required classes
import java.util.*;
import java.text.NumberFormat;
import java.util.Locale;

// Main class
class GFG {

    // Main driver method  
    public static void main(String args[])
    {
        // Creating an object of NumberFormat class
        NumberFormat nf
            = NumberFormat.getCompactNumberInstance();

        // Print and display commands 
        System.out.println(
            "This method returns in NumberFormat.Style.SHORT:");
        System.out.println("Result: " + nf.format(100));
        System.out.println("Result: " + nf.format(10000));
        System.out.println("Result: " + nf.format(120300));
        System.out.println("Result: " + nf.format(2120000));
        System.out.println("Result: "
                           + nf.format(1240000300));
    }
}
```

**输出:**

```
This method returns in NumberFormat.Style.SHORT:
Result: 100
Result: 10K
Result: 120K
Result: 2M
Result: 1B
```

**方法 2:**getcompactnumberstance()

它是 [java.text.NumberFormat](https://www.geeksforgeeks.org/numberformat-class-java/) 的一个内置方法，为指定的区域设置和 formatStyle 返回一个紧凑的数字格式。

**语法**:

```
public static NumberFormat getCompactNumberInstance​(Locale locale, NumberFormat.Style formatStyle)
```

**参数:**该功能接受2 个参数:

*   所需的地区
*   格式化数字的样式

**返回值:**紧凑数字格式的数字格式实例

**异常:**如果区域设置或格式样式为空，此方法将抛出 [**空指针异常**](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implement NumberFormat class by
// Illustrating getCompactNumberInstance​() Method

// Importing required classes
import java.text.NumberFormat;
import java.util.Locale;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of NumberFormat class
        NumberFormat nfLong
            = NumberFormat.getCompactNumberInstance(
                Locale.US, NumberFormat.Style.LONG);

        // Print and display commands
        System.out.println(nfLong.format(100));
        System.out.println(nfLong.format(1000));
        System.out.println(nfLong.format(10000));
        System.out.println(nfLong.format(100000));

        // Again creating an object of NumberFormat class
        NumberFormat nfShort
            = NumberFormat.getCompactNumberInstance(
                Locale.US, NumberFormat.Style.SHORT);

        // Print and display commands
        System.out.println(nfShort.format(100));
        System.out.println(nfShort.format(1000));
        System.out.println(nfShort.format(10000));
        System.out.println(nfShort.format(100000));
    }
}
```

**输出:**

```
100
1 thousand
10 thousand
100 thousand
100
1K
10K
100K
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implement NumberFormat class by
// Illustrating getCompactNumberInstance​() Method

// Importing required classes
import java.text.NumberFormat;
import java.util.Locale;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {
        // Creating an object of NumberFormat class
        NumberFormat fmt
            = NumberFormat.getCompactNumberInstance(
                Locale.US, NumberFormat.Style.LONG);

        // Print and display commands
        System.out.println(fmt.parse("100"));
        System.out.println(fmt.parse("1 thousand"));
        System.out.println(fmt.parse("10 thousand"));
        System.out.println(fmt.parse("100 thousand"));
    }
}
```

**输出:**

```
100
1000
10000
100000
```

> **注意:**在上面的程序中，我们使用了 fmt.parse()方法将紧凑数字解析成 LONG 模式。