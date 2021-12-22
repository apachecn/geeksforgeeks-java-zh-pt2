# Java 中的随机 setSeed()方法，带示例

> 原文:[https://www . geesforgeks . org/random-set seed-method-in-Java-with-examples/](https://www.geeksforgeeks.org/random-setseed-method-in-java-with-examples/)

**随机类**的 **setSeed()** 方法使用单个长种子设置随机数生成器的种子。

**语法:**

```
public void setSeed() 

```

**参数:**该函数接受单个参数**种子**作为初始种子。

**返回值:**这个方法没有返回值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.Random.setSeed()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // return the next pseudorandom integer value
        System.out.println("Random Integer value : "
                           + r.nextInt());

        // setting seed
        long s = 24;

        r.setSeed(s);

        // value after setting seed
        System.out.println("Random Integer value : " + r.nextInt());
    }
}
```

**Output:**

```
Random Integer value : -2053473769
Random Integer value : -1152406585

```

**程序 2:**

```
// program to demonstrate the
// function java.util.Random.setSeed()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // return the next pseudorandom integer value
        System.out.println("Random Integer value : "
                           + r.nextInt());

        // setting seed
        long s = 29;

        r.setSeed(s);

        // value after setting seed
        System.out.println("Random Integer value : "
                           + r.nextInt());
    }
}
```

**Output:**

```
Random Integer value : -388369680
Random Integer value : -1154330330

```