# Java 中的 StrictMath log10()方法

> 原文:[https://www . geesforgeks . org/strict math-log 10-method-in-Java/](https://www.geeksforgeeks.org/strictmath-log10-method-in-java/)

java . lang . strict math . log 10()是 Java 中的一个内置方法，它接受一个双精度值作为参数，并返回该值的*10 底对数*。从而计算给定参数的基数为 10 的对数值。

**语法:**

```
public static double log10(*double val*)
```

**参数:**该函数接受一个双精度值，*值*作为参数，其*底 10* 对数被计算。

**返回值:**该函数根据以下条件返回*值的以 10 为底的对数*:

*   如果传递的参数是 NaN 或小于零，则函数返回 **NaN**
*   如果传递的参数是*正无穷大*，则函数返回*正无穷大*
*   如果传递的参数是*零*，则函数返回*负无穷大*。
*   如果传递的参数是![10^a](img/a9f4a64525a96ae4ebfafee9344644da.png "Rendered by QuickLaTeX.com")，则函数返回 **a**

**示例:**

```
Input : 2018.0
Output : 7.609862200913554

Input : 1000000.0
Output : 6.0

```

以下程序说明了**Java . lang . strict math . log 10()**的工作原理:

**程序 1:** 在这个程序中，有限的非零参数作为参数传递。

```
// Java Program to illustrate 
// StrictMath.log10() function 

import java.io.*;
import java.lang.*;

class GFG {
     public static void main(String[] args) {

      double val1 = 2018.00567 , val2 = 100000.0; 

      // Argument passed is infinite
      System.out.println("Base 10 Logarithm of " + val1 + 
                    " is " + StrictMath.log10(val1));

    // Passing zero as argument
      System.out.println("Base 10 Logarithm of "+ val2 
                      +" is "+ StrictMath.log10(val2));

   }
}
```

**Output:**

```
Base 10 Logarithm of 2018.00567 is 3.3049223821418496
Base 10 Logarithm of 100000.0 is 5.0

```

**程序 2:** 在本程序中，无穷大和零作为参数传递。

```
// Java Program to illustrate
// StrictMath.log10() function 

import java.io.*;
import java.lang.*;

class GFG {
     public static void main(String[] args) {

      double val = 2018/(0.0); 

      System.out.println("Base 10 Logarithm of " + val + 
                    " is " + StrictMath.log10(val));

      System.out.println("Base 10 Logarithm of 0 is "
                            + StrictMath.log10(0));

   }
}
```

**Output:**

```
Base 10 Logarithm of Infinity is Infinity
Base 10 Logarithm of 0 is -Infinity

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/strict math . html # log10()](https://docs.oracle.com/javase/8/docs/api/java/lang/StrictMath.html#log())