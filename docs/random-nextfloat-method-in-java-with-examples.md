# Java 中的随机 nextFloat()方法，示例

> 原文:[https://www . geesforgeks . org/random-next float-method-in-Java-with-examples/](https://www.geeksforgeeks.org/random-nextfloat-method-in-java-with-examples/)

**随机类**的 **nextFloat()** 方法从随机数生成器的序列中返回 0.0 到 1.0 之间的下一个伪随机、均匀分布的浮点值。

**语法:**

```
public float nextFloat() 

```

**参数:**函数不接受任何参数。

**返回值:**此方法返回 0.0 到 1.0 之间的下一个伪随机浮点数。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.Random.nextFloat()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // create random object
        Random r = new Random();

        // check next float value and printing it
        System.out.println("Next float value is = "
                           + r.nextFloat());
    }
}
```

**Output:**

```
Next float value is = 0.25155503

```

**程序 2:**

```
// program to demonstrate the
// function java.util.Random.nextFloat()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // create random object
        Random r = new Random();

        // check next float value and printing it
        System.out.println("Next float value is = "
                           + r.nextFloat());
    }
}
```

**Output:**

```
Next float value is = 0.7730949

```