# ZoneId 等于()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/zoneid-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/zoneid-equals-method-in-java-with-examples/)

**等于()**区域标识**类的**方法，用于将该区域标识与作为参数传递的区域标识对象进行比较。此方法返回的值确定如下:

*   如果两个 ZoneId 相等，则返回 true
*   如果两个 ZoneId 不相等，则返回 false。

**语法:**

```
public boolean equals(Object obj)

```

**参数:**该方法接受单个参数 **obj** ，该参数代表要与该 ZoneId 进行比较的对象，不能为空。

**返回值:**如果两个 ZoneId 相等则此方法返回**真**否则返回**假**。

下面的程序说明了 equals()方法:
**程序 1:**

```
// Java program to demonstrate
// ZoneId.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two diff ZoneId objects
        ZoneId ZoneId1
            = ZoneId.of("Europe/Paris");

        ZoneId ZoneId2
            = ZoneId.of("Asia/Calcutta");

        // apply equals() method to check
        // whether both ZoneIds are equal or not
        boolean response = ZoneId1.equals(ZoneId2);

        // print result
        System.out.println("Both ZoneIds"
                           + "are equal: " + response);
    }
}
```

**Output:**

```
Both ZoneIdsare equal: false

```

**程序 2:**

```
// Java program to demonstrate
// ZoneId.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two diff ZoneId objects
        ZoneId ZoneId1
            = ZoneId.of("Asia/Calcutta");

        ZoneId ZoneId2
            = ZoneId.of("Asia/Calcutta");

        // apply equals() method to check
        // whether both ZoneIds are equal or not
        boolean response = ZoneId1.equals(ZoneId2);

        // print result
        System.out.println("Both ZoneIds"
                           + "are equal: " + response);
    }
}
```

**Output:**

```
Both ZoneIdsare equal: true

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/zoneid . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/ZoneId.html#equals(java.lang.Object))