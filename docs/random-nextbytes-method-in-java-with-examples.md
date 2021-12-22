# Java 中的随机 nextBytes()方法，示例

> 原文:[https://www . geesforgeks . org/random-next bytes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/random-nextbytes-method-in-java-with-examples/)

**随机类**的 **nextBytes()** 方法将生成的随机字节放入用户提供的字节数组中。

**语法:**

```java
public void nextBytes(byte[] bytes)  

```

**参数:**该函数接受单个参数**字节**，该参数是放置随机字节的非空字节数组。

**返回值:**这个方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```java
// program to demonstrate the
// function java.util.Random.nextBytes()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // create byte array
        byte[] bytes = new byte[10];

        // put the next byte in the array
        r.nextBytes(bytes);

        // print random value of array
        System.out.print("Random bytes = [ ");
        for (int i = 0; i < bytes.length; i++) {
            System.out.printf("%d ", bytes[i]);
        }
        System.out.print("]");
    }
}
```

**Output:**

```java
Random bytes = [ -90 -126 -75 50 -117 -13 -55 -63 -117 47 ]

```

**程序 2:**

```java
// program to demonstrate the
// function java.util.Random.nextBytes()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // create byte array
        byte[] bytes = new byte[15];

        // put the next byte in the array
        r.nextBytes(bytes);

        // print random value of array
        System.out.print("Random bytes = [ ");
        for (int i = 0; i < bytes.length; i++) {
            System.out.printf("%d ", bytes[i]);
        }
        System.out.print("]");
    }
}
```

**Output:**

```java
Random bytes = [ -82 75 -105 41 -34 94 81 10 -107 -46 37 4 -1 100 -119 ]

```