# Java 中的属性 forEach(双消费者)方法，示例

> 原文:[https://www . geeksforgeeks . org/properties-foreachbiconsumer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-foreachbiconsumer-method-in-java-with-examples/)

**[属性类](https://www.geeksforgeeks.org/java-util-properties-class-java/)** 的 **forEach(双消费者)**方法对哈希表的每个条目执行双消费者操作，直到所有条目都已处理完毕或操作引发异常。双用户操作是以迭代顺序执行的哈希表键值对的函数操作。方法遍历哈希表的每个元素，直到该方法处理完所有元素或者发生异常。操作引发的异常被传递给调用方。

**语法:**

```
public void forEach(BiConsumer action)
```

**参数:**该方法接受一个双消费者类型的参数**动作**，该参数表示要对属性元素执行什么动作。

**返回:**此方法不返回任何内容。

**异常:**如果动作为空，该方法抛出**空指针异常**。

下面的程序说明了 forEach(双消费者)方法:

**程序 1:**

```
// Java program to demonstrate
// forEach(BiConsumer) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();
        properties.put("Pen", 10);
        properties.put("Book", 500);
        properties.put("Clothes", 400);
        properties.put("Mobile", 5000);

        // Print Properties details
        System.out.println("Properties 1: "
                           + properties.toString());

        // Add 100 in each value using forEach()
        properties.forEach((k, v) -> {

            v = (int)v + 100;
            properties.replace(k, v);
        });

        // Print new mapping using forEcah()
        properties.forEach(
            (k, v) -> System.out.println("Key : " + k + ", Value : " + v));
    }
}
```

**输出:**

```
Properties 1: {Book=500, Mobile=5000, Pen=10, Clothes=400}
Key : Clothes, Value : 500
Key : Mobile, Value : 5100
Key : Pen, Value : 110
Key : Book, Value : 600

```

**程序 2:** 显示空指针异常

```
// Java program to demonstrate
// forEach(BiConsumer) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // Create a properties and add some values
        Properties properties = new Properties();

        properties.put(1, "100RS");
        properties.put(2, "500RS");
        properties.put(3, "1000RS");

        // Print Properties details
        System.out.println("Current Properties: "
                           + properties.toString());

        try {

            // add 100 in each value using forEach()
            properties.forEach((k, v) -> {

                v = (String)v + "100";
                properties.put(null, v);
            });
        }
        catch (Exception e) {

            System.out.println("Exception: " + e);
        }
    }
}
```

T5】输出:

```
Current Properties: {3=1000RS, 2=500RS, 1=100RS}
Exception: java.lang.NullPointerException

```

参考文献:[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # forEach-Java . util . function . bicon summer-](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#forEach-java.util.function.BiConsumer-)