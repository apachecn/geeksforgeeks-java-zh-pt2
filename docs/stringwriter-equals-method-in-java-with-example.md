# Java 中 StringWriter 等于()方法，示例

> 原文:[https://www . geesforgeks . org/stringwriter-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/stringwriter-equals-method-in-java-with-example/)

**爪哇**T2T4。Java 中 StringWriter 类的 equals(Object obj)** 方法用于检查 StringWriter 的两个实例是否相等。它返回一个布尔值，说明它们是否相等。**

**签名:**

> 公共布尔等于(StringWriter second _ StringWriter)

**语法:**

```
first_StringWriter.equals(second_StringWriter)
```

**参数:**该方法接受一个强制参数 **second_StringWriter** ，该参数是指要与第一个 StringWriter 进行比较的第二个 StringWriter。

**返回值:**该方法返回**真**如果等式成立，并且对象和字符串书写器都相等，则返回**假**。

下面的程序用来说明 java.io.StringWriter.elements()方法的工作原理:

**程序 1:**

```
// Java code to illustrate the equals() method

import java.io.*;

public class StringWriter_Demo {
    public static void main(String[] args)
    {

        // Creating an empty StringWriter
        StringWriter writer1 = new StringWriter();

        // Inserting elements into the StringWriter
        writer1.write("GeeksForGeeks");

        // Displaying the StringWriter
        System.out.println("StringWriter 1: "
                           + writer1.toString());

        // Creating an empty StringWriter
        StringWriter writer2 = new StringWriter();

        // Inserting elements into the StringWriter
        writer2.write("GFG");

        // Displaying the StringWriter
        System.out.println("StringWriter 2: "
                           + writer2.toString());

        System.out.println("Are both of them equal? "
                           + writer1.equals(writer2));
    }
}
```

**Output:**

```
StringWriter 1: GeeksForGeeks
StringWriter 2: GFG
Are both of them equal? false

```

**程序 2:**

```
// Java code to illustrate the equals() method

import java.io.*;

public class StringWriter_Demo {
    public static void main(String[] args)
    {

        // Creating an empty StringWriter
        StringWriter writer1 = new StringWriter();

        // Inserting elements into the StringWriter
        writer1.write("GFG");

        // Displaying the StringWriter
        System.out.println("StringWriter 1: "
                           + writer1.toString());

        // Creating an empty StringWriter
        StringWriter writer2 = new StringWriter();

        // Inserting elements into the StringWriter
        writer2.write("GFG");

        // Displaying the StringWriter
        System.out.println("StringWriter 2: "
                           + writer2.toString());

        System.out.println("Are both of them equal? "
                           + writer1.equals(writer2));
    }
}
```

**Output:**

```
StringWriter 1: GFG
StringWriter 2: GFG
Are both of them equal? false

```