# Java 中 Writer 等于()方法，示例

> 原文:[https://www . geesforgeks . org/writer-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/writer-equals-method-in-java-with-examples/)

Java 中 [Writer 类](https://www.geeksforgeeks.org/java-io-writer-class-java/)的**Java . io . Writer . equals(Object obj)**方法用于检查 Writer 的两个实例是否相等。它返回一个布尔值，说明它们是否相等。

**签名:**

```
public boolean equals(Writer second_Writer)
```

**语法:**

```
first_Writer.equals(second_Writer)
```

**参数:**此方法接受一个强制参数 **second_Writer** ，该参数是指要与第一个 Writer 进行比较的第二个 Writer。

**返回值:**该方法返回**真**如果等式成立，并且对象和编写器都相等，则返回**假**。

下面的程序用来说明 java.io.Writer.elements()方法的工作原理:

**程序 1:**

```
// Java code to illustrate the equals() method

import java.io.*;

public class Writer_Demo {
    public static void main(String[] args)
    {

        try {
            // Creating an empty Writer
            Writer writer1 = new PrintWriter(System.out);

            // Inserting elements into the Writer
            writer1.write("GeeksForGeeks");

            // Displaying the Writer
            System.out.println("Writer 1: "
                               + writer1.toString());

            // Creating an empty Writer
            Writer writer2 = new PrintWriter(System.out);

            // Inserting elements into the Writer
            writer2.write("GFG");

            // Displaying the Writer
            System.out.println("Writer 2: "
                               + writer2.toString());

            System.out.println("Are both of them equal? "
                               + writer1.equals(writer2));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Writer 1: java.io.PrintWriter@232204a1
Writer 2: java.io.PrintWriter@4aa298b7
Are both of them equal? false

```

**程序 2:**

```
// Java code to illustrate the equals() method

import java.io.*;

public class Writer_Demo {
    public static void main(String[] args)
    {

        try {
            // Creating an empty Writer
            Writer writer1 = new PrintWriter(System.out);

            // Inserting elements into the Writer
            writer1.write("GFG");

            // Displaying the Writer
            System.out.println("Writer 1: "
                               + writer1.toString());

            // Creating an empty Writer
            Writer writer2 = new PrintWriter(System.out);

            // Inserting elements into the Writer
            writer2.write("GFG");

            // Displaying the Writer
            System.out.println("Writer 2: "
                               + writer2.toString());

            System.out.println("Are both of them equal? "
                               + writer1.equals(writer2));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Writer 1: java.io.PrintWriter@232204a1
Writer 2: java.io.PrintWriter@4aa298b7
Are both of them equal? false

```