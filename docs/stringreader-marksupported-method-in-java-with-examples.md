# Java 中 StringReader markSupported()方法，示例

> 原文:[https://www . geeksforgeeks . org/string reader-marksupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringreader-marksupported-method-in-java-with-examples/)

Java 中 **[StringReader](https://www.geeksforgeeks.org/java-io-stringreader-class-java/)** 类的 **markSupported()** 方法，用来检查这个 StringReader 是否支持 mark()操作。它返回一个布尔值，该值表示读取器是否被标记为受支持。

**语法:**

```java
public boolean markSupported()
```

**参数:**该方法不接受任何参数

**返回值:**这个方法返回一个**布尔值**，告诉这个 StringReader 是否支持 mark()操作。如果它是 markSupported，则返回 true。否则返回假。

下面的方法说明了 markSupported()方法的工作原理:

**程序 1:**

```java
// Java program to demonstrate
// StringReader markSupported() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            String str = "GeeksForGeeks";

            // Create a StringReader instance
            StringReader reader
                = new StringReader(str);

            // Check if the StringReader is
            // markSupported using markSupported()
            System.out.println("Is StringReader markSupported: "
                               + reader.markSupported());

            reader.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Is StringReader markSupported: true

```

**程序二:**

```java
// Java program to demonstrate
// StringReader markSupported() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        try {
            String str = "GeeksForGeeks";

            // Create a StringReader instance
            StringReader reader
                = new StringReader(str);

            // Check if the StringReader is
            // markSupported using markSupported()
            System.out.println("Is StringReader markSupported: "
                               + reader.markSupported());

            reader.close();
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Is StringReader markSupported: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/io/stringreader . html # markSupported–](https://docs.oracle.com/javase/9/docs/api/java/io/StringReader.html#markSupported--)