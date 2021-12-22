# 为什么 Java 集合不能直接存储原语类型？

> 原文:[https://www . geesforgeks . org/why-Java-collections-不能-直接-存储-原语-类型/](https://www.geeksforgeeks.org/why-java-collections-cannot-directly-store-primitives-types/)

[原语类型](https://www.geeksforgeeks.org/primitive-data-type-vs-object-data-type-in-java-with-examples/)是 Java 语言中最基本的数据类型。这种类型只有一个目的——包含一种纯粹的、简单的值。由于 java 是一种静态类型的语言，其中每个变量和表达式类型在编译时都是已知的，因此您不能为这样的基元类型定义新的操作。

插图:

```
Invalid : vector.addElement(3) ;
Valid   : vector.addElelment("3") ;
```

**结论:**

*   Java 基元类型不是引用类型。例如，int 不是一个对象。
*   Java 使用引用类型的类型擦除来做泛型。例如，一个列表>在运行时实际上是一个列表<object>。</object>

[集合](https://www.geeksforgeeks.org/collections-in-java-2/) 是用来存储和操纵一组对象的框架。Java 集合意味着一个单一的对象单元。由于上面的两种说法都是正确的，泛型 Java 集合不能直接存储原语类型。

> [包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)提供了一种使用原始数据类型(int、boolean 等)的方法..)作为对象或包装器类是一个类，其对象包装或包含基本数据类型。它产生了以下两个概念:
> 
> 1.  汽车人
> 2.  取消订阅

<figure class="table">

| 原始数据类型 | 包装类 |
| --- | --- |
| 字节 | 字节 |
| 短的 | 短的 |
| （同 Internationalorganizations）国际组织 | 整数 |
| 长的 | 长的 |
| 漂浮物 | 浮动 |
| 两倍 | 两倍 |
| 布尔 | 布尔代数学体系的 |
| 茶 | 性格；角色；字母 |

</figure>

[自动装箱](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)是将原语类型自动转换为其对应包装类的对象，称为自动装箱。例如:

*   整数到整数的转换
*   长到长的转换
*   将双精度转换为双精度等。

[拆箱](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)只是自动装箱的反向过程。将包装类的对象自动转换为其对应的基元类型称为取消装箱。例如–整数到整数、长到长、双到双等的转换。

**插图:** [【自动分类】](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Importing input output classes
import java.io.*;

class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Custom input
        Integer i = new Integer(21);

        // Boxing
        Integer j = 5;
        System.out.println("i=" + i + "\n j=" + j);
    }
}
```

**输出:**

```
i=21
j=5
```

**插图 2:** [脱氧](https://www.geeksforgeeks.org/autoboxing-unboxing-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Import input output classes
import java.io.*;

// Class
public class GFG {

    // MAin driver method
    public static void main(String args[])
    {

        // Custom input
        Integer i = new Integer(50);

        // Unboxing
        int a = i;

        // Unboxing
        int b = i.intValue();

        // Print and display
        System.out.println("a=" + a + "\nb=" + b);
    }
}
```