# Java 中的属性清除()方法，示例

> 原文:[https://www . geesforgeks . org/properties-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-clear-method-in-java-with-examples/)

方法用于从属性实例中移除所有元素。使用 clear()方法只会清除属性中的所有元素，而不会删除属性。换句话说，我们可以说 clear()方法仅用于清空现有的属性。

**语法:**

```java
public void clear()
```

**参数:**该方法不取任何参数

**返回值:**函数不返回值。

下面的程序说明了 Java.util.Properties.clear()方法。

**例 1:**

```java
// Java code illustrating clear() method

import java.util.*;

class PropertiesDemo {
    public static void main(String arg[])
    {
        Properties gfg = new Properties();
        Set URL;
        String str;

        gfg.put("ide",
                "ide.geeksforgeeks.org");
        gfg.put("contribute",
                "write.geeksforgeeks.org");
        gfg.put("quiz",
                "quiz.geeksforgeeks.org");

        // checking what's in table
        System.out.println("Current Properties: "
                           + gfg.toString());

        System.out.println("\nClearing the Properties");
        gfg.clear();

        // checking what's in table now
        System.out.println("New Properties: "
                           + gfg.toString());
    }
}
```

**Output:**

> 当前属性:{ contribute = write . geesforgeeks . org，quick = quick . geesforgeeks . org，ide = ide . geesforgeeks . org }
> 
> 清除属性
> 新属性:{}

**例 2:**

```java
// Java code illustrating clear() method

import java.util.*;

class PropertiesDemo {
    public static void main(String arg[])
    {
        Properties gfg = new Properties();
        Set URL;
        String str;

        gfg.put(1, "Geeks");
        gfg.put(2, "GeeksforGeeks");
        gfg.put(3, "Geek");

        // checking what's in table
        System.out.println("Current Properties: "
                           + gfg.toString());

        System.out.println("\nClearing the Properties");
        gfg.clear();

        // checking what's in table now
        System.out.println("New Properties: "
                           + gfg.toString());
    }
}
```

**Output:**

> 当前属性:{ 3 =极客，2 =极客暴客，1 =极客}
> 
> 清除属性
> 新属性:{}

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # clear–](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#clear--)