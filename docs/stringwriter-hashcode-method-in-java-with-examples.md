# Java 中 StringWriter hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/stringwriter-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringwriter-hashcode-method-in-java-with-examples/)

Java 中 **[StringWriter](https://www.geeksforgeeks.org/java-io-stringwriter-class-in-java/)** 类的 **hashCode()** 方法用来获取这个 StringWriter 实例的 hashCode 值。此方法不接受任何参数，并返回所需的 int 值。

**语法:**

```
public int hashCode()
```

**参数:**此方法接受不接受任何参数。

**返回值:**这个方法返回**一个 int 值**，它是 StringWriter 实例的 HashCode 值。

下面的方法说明了 hashCode()方法的工作原理:

**程序 1:**

```
// Java program to demonstrate
// StringWriter hashCode() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter StringWriter
                = new StringWriter();

            // Get the String
            // to be written in the stream
            String string = "GeeksForGeeks";

            // Write the string
            // to this StringWriter using write() method
            StringWriter.write(string);

            // Get the HashCode value using hashCode()
            System.out.println("HashCode value: "
                               + StringWriter.hashCode());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
HashCode value: 589431969

```

**程序 2:**

```
// Java program to demonstrate
// StringWriter hashCode() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        try {

            // Create a StringWriter instance
            StringWriter StringWriter
                = new StringWriter();

            // Get the String
            // to be written in the stream
            String string = "GFG";

            // Write the string
            // to this StringWriter using write() method
            StringWriter.write(string);

            // Get the HashCode value using hashCode()
            System.out.println("HashCode value: "
                               + StringWriter.hashCode());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
HashCode value: 589431969

```