# 用示例将 isAnnotationPresent()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-is notationpresent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-isannotationpresent-method-in-java-with-examples/)

**java.lang.Package 类**的**is notationpresent()**方法用于检查该类中是否存在指定注释类型的注释。方法返回一个从相同开始的布尔值。

**语法:**

```
public boolean isAnnotationPresent(Class<T> annotationClass)
```

**参数:**该方法接受一个参数**标注类**，即要获取的标注类型。
**返回值:**此方法返回**布尔值**起始相同。
**异常:**此方法抛出:

*   **NullPointRexception:**如果给定的注释类为空。

下面的程序演示了 isAnnotationPresent()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isAnnotationPresent() method

import java.util.*;
import java.lang.annotation.*;

// create a custom Annotation
@Retention(RetentionPolicy.RUNTIME)
@interface Annotation {

    // This annotation has two attributes.
    public String key();

    public String value();
}

// call Annotation for method
// and pass values for annotation
@Annotation(key = "GFG", value = "GeeksForGeeks")
public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if there is any annotation
        // using isAnnotationPresent() method
        System.out.println(
            "If there is any annotation in myClass: "
            + myClass.isAnnotationPresent(
                  Annotation.class));
    }
}
```

**输出:**

> 由 myClass 表示的类:类测试
> 如果 myClass 中有标注:true

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isAnnotationPresent() method

import java.util.*;
import java.lang.annotation.*;

// Class with no annotations
public class Test {

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the annotation
        // using isAnnotationPresent() method
        System.out.println(
            "If there is any annotation in myClass: "
            + myClass.isAnnotationPresent(
                  Annotation.class));
    }
}
```

**输出:**

> 由 myClass 表示的类:类测试
> 如果 myClass 中有标注:false

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # is notationpresent-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#isAnnotationPresent-java.lang.Class-)