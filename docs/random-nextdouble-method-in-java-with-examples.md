# Java 中的随机 nextDouble()方法，示例

> 原文:[https://www . geesforgeks . org/random-next double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/random-nextdouble-method-in-java-with-examples/)

**随机类**的 **nextDouble()** 方法从这个随机数发生器的序列中返回下一个伪随机的、均匀分布的双数值 0.0 到 1.0。

**语法:**

```java
public double nextDouble()  

```

**参数:**函数不接受任何参数。

**返回值:**这个方法从这个随机数发生器的序列中返回下一个伪随机的、均匀分布的 0.0 到 1.0 之间的双值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.Random.nextDouble()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // check next double value  and print it
        System.out.println("Next double value is = "
                           + r.nextDouble());
    }
}
```

**Output:**

```java
Next double value is = 0.10210556893379474

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.Random.nextDouble()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // check next double value  and print it
        System.out.println("Next double value is = "
                           + r.nextDouble());
    }
}
```

**Output:**

```java
Next double value is = 0.26964189606000966

```