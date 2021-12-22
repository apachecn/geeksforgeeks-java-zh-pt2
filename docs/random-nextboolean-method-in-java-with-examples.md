# Java 中的随机 nextBoolean()方法，示例

> 原文:[https://www . geesforgeks . org/random-next boolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/random-nextboolean-method-in-java-with-examples/)

**随机类**的**下一个布尔值()**方法从随机数生成器的序列中返回下一个伪随机的、均匀分布的布尔值。

**语法:**

```java
public boolean nextBoolean()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回下一个伪随机的、均匀分布的布尔值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.Random.nextBoolean()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // create random object
        Random random = new Random();

        // get boolean value
        System.out.println("Random boolean value is : "
                           + random.nextBoolean());
    }
}
```

**Output:**

```java
Random boolean value is : true

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.Random.nextBoolean()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // create random object
        Random random = new Random();

        // get boolean value
        System.out.println("Random boolean value is : "
                           + random.nextBoolean());
    }
}
```

**Output:**

```java
Random boolean value is : false

```