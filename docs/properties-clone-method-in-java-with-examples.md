# Java 中的属性克隆()方法，示例

> 原文:[https://www . geesforgeks . org/properties-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/properties-clone-method-in-java-with-examples/)

使用**Java . util . Properties . clone()**方法创建该实例的浅拷贝，其中包含该 Properties 实例的所有元素。

**语法:**

```java
public Object clone()
```

**参数:**该方法不取任何参数

**返回值:**函数返回克隆的对象，它是这个属性实例的浅拷贝。

下面的程序说明了 Java.util.Properties.clone()方法。

**例 1:**

```java
// Java code illustrating clone() method

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

        System.out.println("\nCloning the Properties");
        Properties cloned = (Properties)gfg.clone();

        // checking what's in table now
        System.out.println("Cloned Properties: "
                           + cloned.toString());
    }
}
```

**Output:**

> 当前属性:{ contribute = write . geesforgeeks . org，quick = quick . geesforgeeks . org，ide = ide . geesforgeeks . org }
> 
> 克隆属性
> 克隆的属性:{ contribute = write . geeksforgeeks . org，quick = quick . geeksforgeeks . org，ide=ide.geeksforgeeks.org}

**例 2:**

```java
// Java code illustrating clone() method

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

        System.out.println("\nCloning the Properties");
        Properties cloned = (Properties)gfg.clone();

        // checking what's in table now
        System.out.println("Cloned Properties: "
                           + cloned.toString());
    }
}
```

**Output:**

> 当前属性:{ 3 =极客，2 =极客暴客，1 =极客}
> 
> 克隆属性
> 克隆的属性:{ 3 =极客，2 =极客，1 =极客}

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/properties . html # clone–](https://docs.oracle.com/javase/9/docs/api/java/util/Properties.html#clone--)