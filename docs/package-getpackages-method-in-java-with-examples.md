# 用 Java 打包 getPackages()方法，示例

> 原文:[https://www . geesforgeks . org/package-getpackages-method-in-Java-with-examples/](https://www.geeksforgeeks.org/package-getpackages-method-in-java-with-examples/)

**[java.lang.Package 类](https://www.geeksforgeeks.org/java-lang-package-java/)** 的 **getPackages()** 方法用于获取调用者的类加载器定义的 Packages。方法将包作为包对象的数组返回。

**语法:**

```
public boolean getPackages(String desiredVersion)

```

**参数:**此方法不接受任何参数。

**返回值:**该方法将包作为包对象的**数组**返回。

下面的程序演示了 getPackages()方法。

**例 1:**

```
// Java program to demonstrate
// getPackages() method

public class Test {
    public static void main(String[] args)
    {

        // get the Packages using getPackages() method
        Package[] packages = Package.getPackages();

        // print all packages, one by one
        for (int i = 0; i < packages.length; i++) {
            System.out.println(packages[i]);
        }
    }
}
```

**输出:**

```
package sun.reflect, Java Platform API Specification, version 1.8
package java.util, Java Platform API Specification, version 1.8
package sun.reflect.annotation, Java Platform API Specification, version 1.8
package java.lang.annotation, Java Platform API Specification, version 1.8
package java.nio, Java Platform API Specification, version 1.8
package sun.nio, Java Platform API Specification, version 1.8
package java.security.cert, Java Platform API Specification, version 1.8
package java.util.zip, Java Platform API Specification, version 1.8
package sun.launcher, Java Platform API Specification, version 1.8
package sun.security.action, Java Platform API Specification, version 1.8
package java.nio.file, Java Platform API Specification, version 1.8
package java.nio.charset, Java Platform API Specification, version 1.8
package sun.net.www, Java Platform API Specification, version 1.8
package java.lang.ref, Java Platform API Specification, version 1.8
package java.net, Java Platform API Specification, version 1.8
package sun.net.www.protocol.file, Java Platform API Specification, version 1.8
package java.lang.invoke, Java Platform API Specification, version 1.8
package sun.util.locale, Java Platform API Specification, version 1.8
package sun.reflect.generics.repository, Java Platform API Specification, version 1.8
package sun.misc, Java Platform API Specification, version 1.8
package java.lang.reflect, Java Platform API Specification, version 1.8
package sun.net.util, Java Platform API Specification, version 1.8
package java.security, Java Platform API Specification, version 1.8
package sun.net.www.protocol.jar, Java Platform API Specification, version 1.8
package java.util.concurrent, Java Platform API Specification, version 1.8
package java.util.concurrent.atomic, Java Platform API Specification, version 1.8
package java.util.concurrent.locks, Java Platform API Specification, version 1.8
package sun.util, Java Platform API Specification, version 1.8
package java.lang, Java Platform API Specification, version 1.8
package java.io, Java Platform API Specification, version 1.8
package sun.reflect.misc, Java Platform API Specification, version 1.8
package sun.nio.ch, Java Platform API Specification, version 1.8
package java.util.jar, Java Platform API Specification, version 1.8
package sun.nio.cs, Java Platform API Specification, version 1.8
package java.util.function, Java Platform API Specification, version 1.8
package java.nio.charset.spi, Java Platform API Specification, version 1.8
package sun.security.util, Java Platform API Specification, version 1.8

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/package . html # getPackages–](https://docs.oracle.com/javase/9/docs/api/java/lang/Package.html#getPackages--)