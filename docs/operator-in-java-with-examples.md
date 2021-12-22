# &&Java 中的运算符，示例

> 原文:[https://www . geesforgeks . org/operator-in-Java-with-examples/](https://www.geeksforgeeks.org/operator-in-java-with-examples/)

**& &** 是[逻辑运算符](https://www.geeksforgeeks.org/operators-in-java/)的一种，读作“**与**或“**逻辑与**”。该运算符用于执行“逻辑与”运算，即类似于数字电子中 **[与门](https://www.geeksforgeeks.org/digital-logic-logic-gates/)** 的功能。

[![](img/1c9045dcce805fc8e54201bdfc459351.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190930141625/and-gate.jpg)

需要记住的一点是，如果第一个条件为假，则不评估第二个条件，即它具有短路效应。广泛用于测试做决定的几个条件。

**语法:**

```
Condition1 && Condition2

// returns true if both the conditions are true.

```

下面是演示&&运算符的示例:

**示例:**

```
// Java program to illustrate
// logical AND operator

import java.util.*;

public class operators {
    public static void main(String[] args)
    {

        int num1 = 10;
        int num2 = 20;
        int num3 = 30;

        // find the largest number
        // using && operator
        if (num1 >= num2 && num1 >= num3)
            System.out.println(
                num1
                + " is the largest number.");
        else if (num2 >= num1 && num2 >= num3)
            System.out.println(
                num2
                + " is the largest number.");
        else
            System.out.println(
                num3
                + " is the largest number.");
    }
}
```

**Output:**

```
30 is the largest number.

```