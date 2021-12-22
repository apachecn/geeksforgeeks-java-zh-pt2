# Java 中 ObjectInputStream defaultReadObject()方法，带示例

> 原文:[https://www . geesforgeks . org/objectinputstream-defaultreadobject-method-in-Java-with-examples/](https://www.geeksforgeeks.org/objectinputstream-defaultreadobject-method-in-java-with-examples/)

Java 中 **ObjectInputStream** 类的 **defaultReadObject()** 方法用于从该流中读取当前类的非静态和非瞬态字段。

**语法:**

```
public void defaultReadObject()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回已读取的值。

**错误和异常:**函数抛出三个异常，如下所述:

*   **ClassNotFoundException:** 如果找不到序列化对象的类，将引发异常。
*   **IOException:** 如果出现输入/输出错误，将引发异常。
*   **NotActiveException:** 如果流当前没有读取对象，则会引发异常。

下面的程序说明了上面的方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the above method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        try {
            // create a new file
            // with an ObjectOutputStream
            FileOutputStream out
                = new FileOutputStream("Shubham.txt");
            ObjectOutputStream out1
                = new ObjectOutputStream(out);

            // write
            out1.writeObject(new solve());

            // Flushes the stream
            out1.flush();

            // create an ObjectInputStream
            // for the file
            ObjectInputStream example
                = new ObjectInputStream(
                    new FileInputStream("Shubham.txt"));

            // Read from the stream
            solve ans = (solve)example.readObject();
            System.out.println(ans.str);
        }

        catch (Exception ex) {
            ex.printStackTrace();
        }
    }

    static class solve implements Serializable {
        String str = "Geeksforgeeks";

        private void readObject(ObjectInputStream res)
            throws IOException,
                   ClassNotFoundException
        {

            // By using defaultReadObject() method is
            // to read non-static fields of the present
            // class from the ObjectInputStream
            res.defaultReadObject();
        }
    }
}
```

**输出:**

[![](img/e81f57996bd01149f8e45a67a26456f9.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601104449/defobj1.JPG)

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the above method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        try {
            // create a new file
            // with an ObjectOutputStream
            FileOutputStream out
                = new FileOutputStream("Shubham.txt");
            ObjectOutputStream out1
                = new ObjectOutputStream(out);

            // write
            out1.writeObject(new solve());

            // Flushes the stream
            out1.flush();

            // create an ObjectInputStream
            // for the file
            ObjectInputStream example
                = new ObjectInputStream(
                    new FileInputStream("Shubham.txt"));

            // Read from the stream
            solve ans = (solve)example.readObject();
            // System.out.println(ans.str);
            System.out.println(ans.in);
        }

        catch (Exception ex) {
            ex.printStackTrace();
        }
    }

    static class solve implements Serializable {

        // String str = "Geeksforgeeks";
        Integer in = new Integer(112414);

        private void readObject(ObjectInputStream res)
            throws IOException,
                   ClassNotFoundException
        {
            // By using defaultReadObject() method is
            // to read non-static fields of the present
            // class from the ObjectInputStream
            res.defaultReadObject();
        }
    }
}
```

**输出:**

[![](img/7d11bc2a31486bf0b83a35cee258515c.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601104951/defobj2.JPG)

**参考:**

[https://docs . Oracle . com/javae/10/docs/API/Java/io/object input stream . html # default readobject()](https://docs.oracle.com/javase/10/docs/api/java/io/ObjectInputStream.html#defaultReadObject())