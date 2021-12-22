# Java 中原始数据类型与对象数据类型对比示例

> 原文:[https://www . geesforgeks . org/primitive-data-type-vs-object-data-type-in-Java-with-examples/](https://www.geeksforgeeks.org/primitive-data-type-vs-object-data-type-in-java-with-examples/)

[**原始数据类型**](https://www.geeksforgeeks.org/data-types-in-Java/) **:** 在 Java 中，原始数据类型是 Java 预定义的数据类型。它们指定任何标准值的大小和类型。Java 有 8 种基本数据类型，即字节、短整型、整型、长整型、浮点型、双精度型、字符型和布尔型。当存储一个基本数据类型时，值将被分配到堆栈中。复制一个变量后，会创建该变量的另一个副本，对复制的变量所做的更改不会反映原始变量的更改。这里有一个 Java 程序来演示 Java 中的所有原始数据类型。

[**对象数据类型**](https://www.geeksforgeeks.org/data-types-in-Java/) **:** 这些也被称为非原始或参考数据类型。之所以叫它们，是因为它们指的是任何特定的物体。与基本数据类型不同，非基本数据类型是由用户在 Java 中创建的。例子包括数组、字符串、类、接口等。当引用变量将被存储时，变量将被存储在堆栈中，而原始对象将被存储在堆中。在对象数据类型中，虽然会创建两个副本，但它们都指向堆中的同一个变量，因此对任何变量的更改都会反映这两个变量的更改。这是一个用 Java 演示数组(一种对象数据类型)的 Java 程序。

**Java 中原语和对象数据类型的区别:**

现在让我们来看一个演示 Java 中原语和对象数据类型之间区别的程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.lang.*;
import java.util.*;

class GeeksForGeeks {
    public static void main(String ar[])
    {
        System.out.println("PRIMITIVE DATA TYPES\n");
        int x = 10;
        int y = x;
        System.out.print("Initially: ");
        System.out.println("x = " + x + ", y = " + y);

        // Here the change in the value of y
        // will not affect the value of x
        y = 30;

        System.out.print("After changing y to 30: ");
        System.out.println("x = " + x + ", y = " + y);
        System.out.println(
            "**Only value of y is affected here "
            + "because of Primitive Data Type\n");

        System.out.println("REFERENCE DATA TYPES\n");
        int[] c = { 10, 20, 30, 40 };

        // Here complete reference of c is copied to d
        // and both point to same memory in Heap
        int[] d = c;

        System.out.println("Initially");
        System.out.println("Array c: "
                           + Arrays.toString(c));
        System.out.println("Array d: "
                           + Arrays.toString(d));

        // Modifying the value at
        // index 1 to 50 in array d
        System.out.println("\nModifying the value at "
                           + "index 1 to 50 in array d\n");
        d[1] = 50;

        System.out.println("After modification");
        System.out.println("Array c: "
                           + Arrays.toString(c));
        System.out.println("Array d: "
                           + Arrays.toString(d));
        System.out.println(
            "**Here value of c[1] is also affected "
            + "because of Reference Data Type\n");
    }
}
```

**Output**

```java
PRIMITIVE DATA TYPES

Initially: x = 10, y = 10
After changing y to 30: x = 10, y = 30
**Only value of y is affected here because of Primitive Data Type

REFERENCE DATA TYPES

Initially
Array c: [10, 20, 30, 40]
Array d: [10, 20, 30, 40]

Modifying the value at index 1 to 50 in array d

After modification
Array c: [10, 50, 30, 40]
Array d: [10, 50, 30, 40]
**Here value of c[1] is also affected because of Reference Data Type

```

让我们以表格的方式来看看原语和对象数据类型之间的区别。

<figure class="table">T29

| attribute | original data type | target |
| --- | --- | --- |
| origin | Predefined data types | User defined data type |
| storage organization | Stored in the stack | Reference variables are stored in the stack, and original objects are stored in the stack. |
| Two reference variables are created, but both point to the same object in the heap. |
| When making changes in copied variables | The change of is not reflected in the original variable. | Changes reflected by the original objects. |
| default | The original data type has no null as the default value. | The default value of the reference variable is null |
| example | 字节、短、int、长、浮点、双精度、字符、布尔值 | Array, string class, interface, etc. |

</figure>