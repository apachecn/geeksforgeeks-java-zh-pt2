# | | Java 中的运算符

> 原文:[https://www.geeksforgeeks.org/operator-in-java/](https://www.geeksforgeeks.org/operator-in-java/)

**||** 是[逻辑运算符](https://www.geeksforgeeks.org/operators-in-java/)的一种，读作“**OR**或“**逻辑 OR** ”。该运算符用于执行“逻辑或”运算，即类似于数字电子中 [**或门**](https://www.geeksforgeeks.org/digital-logic-logic-gates/) 的功能。

[![](img/d0ed87611e73b003594eb0de47bef868.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190930142755/OR-gate.jpg)

需要记住的一点是，如果第一个条件为真，则不评估第二个条件，即它具有短路效应。广泛用于测试做决定的几个条件。
**语法:**

```java
Condition1 || Condition2

// returns true if one of the conditions is true.

```

下面是一个示例来演示||运算符:
**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// logical OR operator

import java.util.*;

public class operators {
    public static void main(String[] args)
    {

        char ch = 'a';

        // check if character is alphabet or digit
        // using || operator
        if (ch >= 65 && ch <= 90
            || ch >= 97 && ch <= 122)
            System.out.println(
                ch
                + " is an alphabet.");
        else if (ch >= 48 && ch <= 57)
            System.out.println(
                ch
                + " is a digit.");
        else
            System.out.println(
                ch
                + " is a special character.");
    }
}
```

**Output:** 

```java
a is an alphabet.

```