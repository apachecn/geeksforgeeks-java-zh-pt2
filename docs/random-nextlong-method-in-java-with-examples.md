# Java 中的 Random nextLong()方法，示例

> 原文:[https://www . geesforgeks . org/random-next long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/random-nextlong-method-in-java-with-examples/)

**随机类**的**下一高斯()**方法从这个随机数生成器的序列中返回下一个伪随机的、均匀分布的长值。

**语法:**

```
public long nextLong()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回下一个伪随机的、均匀分布的长值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

```
// program to demonstrate the
// function java.util.Random.nextLong()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // get next long value and print the value
        System.out.println("Long value is = "
                           + r.nextLong());
    }
}
```

**Output:**

```
Long value is = -9027907281942573746

```

```
// program to demonstrate the
// function java.util.Random.nextLong()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // get next long value and print the value
        System.out.println("Long value is = "
                           + r.nextLong());
    }
}
```

**Output:**

```
Long value is = -2817123387200223163

```