# 用示例用 Java 打包 getAnnotationsByType()方法

> 原文:[https://www . geeksforgeeks . org/package-getannotationsbytype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getannotationsbytype-method-in-java-with-examples/)

**java.lang.Package 类**的 **getAnnotationsByType()** 方法用于获取该类中存在的指定注释类型的注释。方法返回指定批注类型的批注数组。

**语法:**

```java
public A[] getAnnotationsByType(Class<T> annotationClass)

```

**参数:**该方法接受一个参数**标注类**，即要获取的标注类型。

**返回值:**该方法返回**指定标注类型的标注数组**。

**异常:**此方法抛出:

*   **NullPointRexception:**如果给定的注释类为空。

下面的程序演示了 getAnnotationsByType()方法。

**例 1:**

```java
// Java program to demonstrate
// getAnnotationsByType() method

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

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println(
            "Class represented by myClass: "
            + myClass.toString());

        // Get the annotation
        // using getAnnotationsByType() method
        System.out.println(
            "Annotation of myClass of type Annotation: "
            + Arrays.toString(
                  myClass
                      .getAnnotationsByType(
                          Annotation.class)));
    }
}
```

**输出:**

> 由 myClass 表示的类:类测试
> 类型的 myClass 的注释注释:[@Annotation(key=GFG，value=GeeksForGeeks)]

**例 2:**

```java
// Java program to demonstrate
// getAnnotationsByType() method

import java.util.*;
import java.lang.annotation.*;

@Deprecated
public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        try {
            // returns the Class object for this class
            Class myClass = Test.class;

            System.out.println(
                "Class represented by myClass: "
                + myClass.toString());

            // Get the annotation
            // using getAnnotationsByType() method
            System.out.println(
                "Annotation of myClass of type Deprecated: "
                + Arrays.toString(
                      myClass
                          .getAnnotationsByType(
                              Deprecated.class)));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

> 由 myClass 表示的类:类测试
> 类型的 myClass 的注释已弃用:[@java.lang.Deprecated()]

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getannocationsbytype-Java . lang . class-](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#getAnnotationsByType-java.lang.Class-)