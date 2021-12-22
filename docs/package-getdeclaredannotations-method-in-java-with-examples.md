# 用示例将 getDeclaredAnnotations()方法打包到 Java 中

> 原文:[https://www . geesforgeks . org/package-getdeclaredannotations-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getdeclaredannotations-method-in-java-with-examples/)

**java.lang.Package 类**的 **getDeclaredAnnotations()** 方法用于获取该类中存在的已声明的注释。方法返回一个已声明注释的数组。

**语法:**

```
public DeclaredAnnotation[] getDeclaredAnnotations()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回**一个声明注释的数组**存在。

下面的程序演示了 getDeclaredAnnotations()方法。

**例 1:**

```
// Java program to demonstrate
// getDeclaredAnnotations() method

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

            // Get the declared annotation
            // using getDeclaredAnnotations() method
            System.out.println(
                "DeclaredAnnotation of myClass: "
                + Arrays.toString(
                      myClass.getDeclaredAnnotations()));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Class represented by myClass: class Test
DeclaredAnnotation of myClass: [@java.lang.Deprecated()]

```

**例 2:**

```
// Java program to demonstrate
// getDeclaredAnnotations() method

import java.util.*;
import java.lang.annotation.*;

// create a custom DeclaredAnnotation
@Retention(RetentionPolicy.RUNTIME)
@interface DeclaredAnnotation {

    // This declared annotation has two attributes.
    public String key();

    public String value();
}

// call DeclaredAnnotation for method
// and pass values for declared annotation
@DeclaredAnnotation(key = "GFG", value = "GeeksForGeeks")
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

        // Get the declared annotation
        // using getDeclaredAnnotations() method
        System.out.println(
            "DeclaredAnnotation of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredAnnotations()));
    }
}
```

**Output:**

> 由 myClass 表示的类:class Test
> DeclaredAnnotation of my class:[@ DeclaredAnnotation(key = GFG，value=GeeksForGeeks)]

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getDeclaredAnnotations–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#getDeclaredAnnotations--)