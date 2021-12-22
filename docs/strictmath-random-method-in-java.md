# Java 中的 StrictMath 随机()方法

> 原文:[https://www . geesforgeks . org/strict math-random-method-in-Java/](https://www.geeksforgeeks.org/strictmath-random-method-in-java/)

**random()** 是 java 中 StrictMath 类的一个内置方法，用于获取一个双精度值，该值带有一个大于或等于 0.0 且小于 1.0 的正数。random()方法被精确地组织起来，以默许多个线程的适当使用。返回的值采用伪随机方式，并在该范围内保持恒定分布。
**语法:**

```
public static double random()
```

**参数:**该方法不接受任何参数。
**返回值:**该方法返回大于等于 0.0 且小于 1.0 的伪随机双精度值。
下面的程序说明了 Java.lang.StrictMath.random()方法:
**程序 1:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.StrictMath.random() Method
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double random_num = StrictMath.random();
    System.out.println("Generated random number = "+ random_num);

    random_num = StrictMath.random();
    System.out.println("Generated random number = "+ random_num);

}
}
```

**Output:** 

```
Generated random number = 0.7276560829796844
Generated random number = 0.6646167632286143
```

**程序 2:**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.StrictMath.random() Method
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    double random_num = StrictMath.random();
    System.out.println("Generated random number = "+ random_num);

    random_num = StrictMath.random();
    System.out.println("Generated random number = "+ random_num);

}
}
```

**Output:** 

```
Generated random number = 0.5071995313935024
Generated random number = 0.6938224427158157
```