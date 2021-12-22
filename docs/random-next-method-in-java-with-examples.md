# Java 中的随机 next()方法，示例

> 原文:[https://www . geesforgeks . org/random-next-method-in-Java-with-examples/](https://www.geeksforgeeks.org/random-next-method-in-java-with-examples/)

**随机类**的 **next()** 方法从随机数发生器的序列中返回下一个伪随机值。

**语法:**

```java
protected int next(int bits)

```

**参数:**该函数接受单个参数**位**，它们是随机位。

**返回值:**此方法返回下一个伪随机数。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.Random.next()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random ran = new Random();

        // generate next random number
        System.out.println("Next value returns = "
                           + ran.nextInt(9));
    }
}
```

**Output:**

```java
Next value returns = 8

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.Random.next()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random ran = new Random();

        // generate next random number
        System.out.println("Next value returns = "
                           + ran.nextInt(55));
    }
}
```

**Output:**

```java
Next value returns = 54

```