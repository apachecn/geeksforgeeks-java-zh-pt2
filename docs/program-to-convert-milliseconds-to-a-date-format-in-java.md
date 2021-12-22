# 用 Java 将毫秒转换为日期格式的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-毫秒-a-date-format-in-java/](https://www.geeksforgeeks.org/program-to-convert-milliseconds-to-a-date-format-in-java/)

给定毫秒。任务是用 Java 编写一个程序，将毫秒转换为日期，以**DD MMM yyy HH:mm:ss:SSS Z**格式显示日期。
Java 中的 Date 类内部以毫秒为单位存储日期。因此，任何日期都是自 1970 年 1 月 1 日格林尼治时间 00:00:00 以来经过的毫秒数，日期类提供了一个构造函数，可用于从毫秒创建日期。
T4 简单日期格式类帮助格式化和解析数据。我们可以将日期从一种格式改为另一种格式。它允许用户将字符串日期格式解释为日期对象。我们可以相应地修改日期。
简单日期格式的构造函数:

*   **简单日期格式(String pattern_arg)** :使用给定的模式–pattern _ arg(默认格式区域设置的默认日期格式符号)构建简单日期格式。
*   **简单日期格式(String pattern_arg，Locale _ Locale _ arg)**:使用给定格式 Locale–Locale _ arg 的给定模式–pattern _ arg(默认日期格式符号)构建简单日期格式。
*   **简单日期格式(字符串模式 _arg，日期格式符号格式符号)**:使用给定的模式–模式 _arg 和日期格式符号构造简单日期格式。

下面是用 Java 将毫秒转换成日期格式的程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert milliseconds
// to a Date format

import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;

public class SectoDate {
    public static void main(String args[])
    {

        // milliseconds
        long milliSec = 3010;

        // Creating date format
        DateFormat simple = new SimpleDateFormat("dd MMM yyyy HH:mm:ss:SSS Z");

        // Creating date from milliseconds
        // using Date() constructor
        Date result = new Date(milliSec);

        // Formatting Date according to the
        // given format
        System.out.println(simple.format(result));
    }
}
```

**Output:** 

```
01 Jan 1970 00:00:03:010 +0000
```