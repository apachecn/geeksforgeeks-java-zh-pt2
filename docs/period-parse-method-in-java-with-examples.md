# Java 中的 Period parse()方法，示例

> 原文:[https://www . geesforgeks . org/period-parse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/period-parse-method-in-java-with-examples/)

**周期类**的 **parse()** 方法用于以 **PnYnMnD** 的形式从给定字符串中获取周期，其中 nY 表示 n 年，nM 表示 n 个月，nD 表示 n 天。

**语法:**

```
public static Period parse(CharSequence text)
```

**参数:**该方法接受单个参数**文本**，这是要解析的字符串。

**返回:**该函数返回**周期**，这是作为参数给出的字符串的解析表示

下面是 Period.parse()方法的实现:

**例 1:**

```
// Java code to demonstrate parse() method
// to obtain period from given string

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be parsed
        String period = "P1Y2M21D";

        // Parse the String into Period
        // using parse() method
        Period p = Period.parse(period);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```
1 Years
2 Months
21 Days

```

**例 2:**

```
// Java code to demonstrate parse() method
// to obtain period from given string

import java.time.Period;

class GFG {
    public static void main(String[] args)
    {

        // Get the String to be parsed
        String period = "-P1Y2M21D";

        // Parse the String into Period
        // using parse() method
        Period p = Period.parse(period);

        System.out.println(p.getYears() + " Years\n"
                           + p.getMonths() + " Months\n"
                           + p.getDays() + " Days");
    }
}
```

**输出:**

```
-1 Years
-2 Months
-21 Days

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/period . html # parse-Java . lang . charsequence-](https://docs.oracle.com/javase/9/docs/api/java/time/Period.html#parse-java.lang.CharSequence-)