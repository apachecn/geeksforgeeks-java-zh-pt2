# Java 中的随机 nextGaussian()方法，示例

> 原文:[https://www . geesforgeks . org/random-next Gaussian-method-in-Java-with-examples/](https://www.geeksforgeeks.org/random-nextgaussian-method-in-java-with-examples/)

**随机类**的**下一个高斯()**方法返回下一个伪随机高斯(正态)分布双值，平均值为 0.0，标准偏差为 1.0，来自随机数发生器的序列。

**语法:**

```
public double nextGaussian()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回下一个均值为 0.0、标准差为 1.0 的伪随机高斯分布双数。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

**程序 1:**

```
// program to demonstrate the
// function java.util.Random.nextGaussian()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // check next Gaussian value and print it
        System.out.println("Next Gaussian value is = "
                           + r.nextGaussian());
    }
}
```

**Output:**

```
Next Gaussian value is = 0.3350871100964153

```

**程序 2:**

```
// program to demonstrate the
// function java.util.Random.nextGaussian()

import java.util.*;
public class GFG {
    public static void main(String[] args)
    {

        // create random object
        Random r = new Random();

        // check next Gaussian value and print it
        System.out.println("Next Gaussian value is = "
                           + r.nextGaussian());
    }
}
```

**Output:**

```
Next Gaussian value is = 1.5685150659018154

```