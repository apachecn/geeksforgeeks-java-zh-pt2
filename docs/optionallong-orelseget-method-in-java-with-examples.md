# Java 中的 OptionalLong orElseGet()方法，带示例

> 原文:[https://www . geesforgeks . org/optional long-or else get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/optionallong-orelseget-method-in-java-with-examples/)

**or lseget([Java . util . function . longsupplier](https://www.geeksforgeeks.org/java-8-longsupplier-interface-with-examples/))**方法帮助我们获取这个 OptionalLong 对象中的值。如果该选项中没有值，则该方法返回作为参数传递的提供函数产生的结果

**语法:**

```
public long orElseGet(LongSupplier supplier)

```

**参数:**该方法接受产生返回值的供给函数。

**返回值:**该方法返回长值(如果存在)，否则返回提供函数产生的结果。

**异常:**如果没有值并且供应函数为空，该方法抛出**空值异常**。

下面的程序说明了 orElseGet([Java . util . function . longsupplier](https://www.geeksforgeeks.org/java-8-longsupplier-interface-with-examples/))方法:

**程序 1:**

```
// Java program to demonstrate
// OptionalLong.orElseGet(LongSupplier) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong oplong = OptionalLong.of(2134);

        // get value using orElseGet
        long value = oplong.orElseGet(() -> getlongValue());

        // prlong value
        System.out.println("value: " + value);
    }

    public static long getlongValue()
    {
        return 3242 + 123;
    }
}
```

**输出:**

```
value: 2134

```

**程序二:**

```
// Java program to demonstrate
// OptionalLong.orElseGet(LongSupplier) method

import java.util.OptionalLong;

public class GFG {

    public static void main(String[] args)
    {

        // create a OptionalLong
        OptionalLong oplong = OptionalLong.empty();

        // get value using orElseGet
        long value = oplong.orElseGet(() -> getlongValue());

        // prlong value
        System.out.println("value: " + value);
    }

    public static long getlongValue()
    {
        return 3242 * 234;
    }
}
```

**输出:**

```
value: 758628

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/optional long . html # orelsget(Java . util . function . longsupplier)](https://docs.oracle.com/javase/10/docs/api/java/util/OptionalLong.html#orElseGet(java.util.function.LongSupplier))