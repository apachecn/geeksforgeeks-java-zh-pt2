# Java 中 ObjectInputStream enableResolveObject()方法，带示例

> 原文:[https://www . geesforgeks . org/objectinputstream-enableresolveobject-method-in-Java-with-examples/](https://www.geeksforgeeks.org/objectinputstream-enableresolveobject-method-in-java-with-examples/)

Java 中 **ObjectInputStream** 类的 **enableResolveObject()** 方法用于使流能够替换从流中读取的对象。启用后，将为每个要反序列化的对象调用 resolveObject(java.lang.Object)方法。

**语法:**

```
protected boolean enableResolveObject(
                        boolean enable)

```

**参数:**该方法只接受单个参数。

*   **启用:**此参数设置为真，以便为每个要反序列化的对象启用 resolveObject()。

**返回值:**此方法返回调用此方法之前的设置。

**错误和异常:**如果安全管理器存在，并且其 checkPermission 方法拒绝允许流替换从流中读取的对象，则函数抛出**安全异常**。

下面的程序说明了上面的方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the above method

import java.io.*;

public class GFG
    extends ObjectInputStream {

    public GFG(InputStream in)
        throws IOException
    {
        super(in);
    }

    public static void main(String[] args)
    {
        String s = "Geeksforgeeks";
        try {

            // create a new file
            // with an ObjectOutputStream
            FileOutputStream out
                = new FileOutputStream("Shubham.txt");

            ObjectOutputStream out1
                = new ObjectOutputStream(out);

            // write
            out1.writeUTF(s);

            // Flushes the stream
            out1.flush();

            // create an ObjectInputStream
            // for the file
            GFG example
                = new GFG(
                    new FileInputStream("Shubham.txt"));

            System.out.println(
                example
                    .resolveObject(
                        example.readUTF()));

            System.out.println(
                example
                    .enableResolveObject(true));
        }

        catch (Exception ex) {
            ex.printStackTrace();
        }
    }
}
```

**输出:**

[![](img/0d1669c8cc64020b14b29407646b8779.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601112613/enableResolveObject1.JPG)

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// the above method

import java.io.*;
import java.io.InputStream;

public class GFG
    extends ObjectInputStream {

    public GFG(InputStream in)
        throws IOException
    {
        super(in);
    }

    public static void main(String[] args)
        throws IOException
    {

        int[] array = { 1, 34, 23, 425, 69, 22 };

        try {

            // create a new file
            // with an ObjectOutputStream
            FileOutputStream out
                = new FileOutputStream("Shubham.txt");

            DataOutputStream out1
                = new DataOutputStream(out);

            // write
            // for each byte in the buffer
            for (int val : array) {

                // write character to the dos
                out1.writeInt(val);
            }

            // Flushes the stream
            out1.flush();

            // create an ObjectInputStream
            // for the file
            DataInputStream example
                = new DataInputStream(
                    new FileInputStream("Shubham.txt"));

            for (int i = 0; i <= array.length; i++) {
                int c = example.readInt();
                System.out.print(c + " ");
            }
            System.out.print("\n");
        }

        catch (Exception ex) {
        }
    }
}
```

**输出:**

[![](img/6f8f13db0758b35cb8ee3fd00ff7557d.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200601112614/enableResolveObject2.JPG)

**参考:**

[https://docs . Oracle . com/javae/10/docs/API/Java/io/object input stream . html # enableresolve object(boolean)](https://docs.oracle.com/javase/10/docs/api/java/io/ObjectInputStream.html#enableResolveObject(boolean))