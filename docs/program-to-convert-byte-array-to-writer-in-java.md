# 用 Java 将字节数组转换为 Writer 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-byte-array-to-writer-in-Java/](https://www.geeksforgeeks.org/program-to-convert-byte-array-to-writer-in-java/)

**参考文献:** [作家类](https://www.geeksforgeeks.org/java-io-writer-class-java/)

**方法:**
Writer 类用于编写字符流，通过它可以将字节数组作为参数传递。通过这种方式，字节数组可以转换成 Writer 类。为了从字符串中获取字节数组，使用了 getBytes()方法。

下面是上述方法的实现:

**程序:**

```java
// Java Program Convert
// Byte Array to Writer

import java.io.StringWriter;
import java.io.Writer;

public class GFG {

    // Method which convert
    // byte array into Writer Class
    static String writeByte(byte[] byteString,
                            byte[] byteInt,
                            byte[] byteChar,
                            byte[] byteDouble)
    {

        // Declare the writer class
        Writer writer = new StringWriter();

        try {
            // Call append() method
            // to append byte array into
            // writer class as append method
            // takes input of only string object
            writer
                .append(new String(byteString)
                        + new String(byteDouble)
                        + new String(byteChar)
                        + new String(byteInt));

            writer.close();
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }

        // return the string
        return writer.toString();
    }

    // Driver Code
    public static void main(String args[])
    {

        String str = "Speed of light: ";
        int num = 8;
        char ch = 'e';
        double dec = 3.0;

        // Insert String value
        byte[] byteString = str.getBytes();

        // Insert int value
        byte[] byteInt = Integer.toString(num).getBytes();

        // Insert char value
        byte[] byteChar = Character.toString(ch).getBytes();

        // Insert double value
        byte[] byteDouble = Double.toString(dec).getBytes();

        // Call the method
        System.out.println(writeByte(byteString, byteInt,
                                     byteChar, byteDouble));
    }
}
```

**Output:**

```java
Speed of light: 3.0e8

```