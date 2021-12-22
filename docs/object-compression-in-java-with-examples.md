# Java 中的对象压缩示例

> 原文:[https://www . geesforgeks . org/object-compression-in-Java-with-examples/](https://www.geeksforgeeks.org/object-compression-in-java-with-examples/)

对象压缩是在各种类和方法的帮助下减小对象大小的过程。然后，接收者通过解压缩被发送者压缩的对象来检索全部信息。请看下图，区分压缩前的文件大小和压缩后的文件大小:

### 对象压缩的需求

在我们需要通过网络传输大量对象的情况下，Java 对象压缩非常有用。对象压缩在发送端完成，在另一端(即接收端)解压缩。通过这种方式，我们可以提高性能，并且可以在两端之间发送和接收大量的对象。

### 对象压缩是如何在 Java 中完成的

Java 对象压缩是使用[gzipoutstream](https://docs.oracle.com/javase/7/docs/api/java/util/zip/GZIPOutputStream.html)类完成的(该类实现了一个流过滤器，用于以 GZIP 文件格式写入压缩数据)，并将其传递给 [ObjectOutputStream](https://docs.oracle.com/javase/7/docs/api/java/io/ObjectOutputStream.html) 类(该类扩展了 [OutputStream](https://docs.oracle.com/javase/7/docs/api/java/io/OutputStream.html) 并实现了 [ObjectOutput](https://docs.oracle.com/javase/7/docs/api/java/io/ObjectOutput.html) 、 [ObjectStreamConstants](https://docs.oracle.com/javase/7/docs/api/java/io/ObjectStreamConstants.html) )以将对象写入外部文件。

我们需要扩展 [Serializable](https://docs.oracle.com/javase/7/docs/api/java/io/Serializable.html) 类，因为我们要压缩的对象将由 User 对象表示。这就是为什么我们需要使用户对象可序列化。

### 对象压缩在 Java 中的实现

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// Object Compression

import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;
import java.io.Serializable;
import java.util.zip.GZIPOutputStream;
import java.io.File;

public class GFG {

    public static void main(String args[])
    {

        // Creating objects of Java Class Bill
        Bill b1
            = new Bill("176BU", "Abhishek Gupta");
        Bill b2
            = new Bill("176DA", "Sushant Singh");
        FileOutputStream f = null;

        // Creates a GZIPOutputStream and
        // initialize it with null
        GZIPOutputStream g = null;

        // Creates an ObjectOutputStream and
        // initialise it with null
        // ObjectOutputStream writes to the
        // defined GZIPOutputStream.
        ObjectOutputStream o = null;

        // Write path of the file in the argument
        File newFile
            = new File("File.dat");
        try {

            // Pass the File object
            // (newFile) to the
            // FileOutputStream
            f = new FileOutputStream(newFile);
            g = new GZIPOutputStream(f);

            // Now pass the GZIPOutputStream object
            // to the ObjectOutputStream
            o = new ObjectOutputStream(g);

            // Writes the object that are going
            // to be compressed to the
            // ObjectOutputStream using
            // writeObject(objectName)
            o.writeObject(b1);
            o.writeObject(b2);

            // flush() API methods of
            // ObjectOutputStream.
            o.flush();
            System.out.println(
                "Process done..");
            System.out.println(
                "Objects are compressed");
        }
        catch (
            FileNotFoundException e) {

            // Catch Block
            System.out.println(
                e.message());
        }
        catch (IOException e) {

            // Catch Block
            System.out.println(
                e.message());
        }
        finally {
            try {

                // Using their
                // close() API methods,
                // closes both
                // the GZIPOutputStream
                // and the
                // ObjectOutputStream
                if (o != null)
                    o.close();
                if (g != null)
                    g.close();
            }
            catch (Exception ex) {

                // Catch block
                System.out.println(
                    ex.message());
            }
        }
    }
}

class Bill implements Serializable {

    // Declaring the private variables
    private String billno;
    private String buyerName;

    // Creating constructor
    // of Java Class Bill
    public Bill(
        String bill, String buyer)
    {
        this.billno = bill;
        this.buyerName = buyer;
    }

    // Defining methods initializing
    // variables billno and buyerName
    public String getBill()
    {
        return billno;
    }
    public void setBill(
        String billno)
    {
        this.billno = billno;
    }
    public String getBuyerName()
    {
        return buyerName;
    }
    public void setBuyerName(
        String buyer)
    {
        this.buyerName = buyer;
    }
}
```

**输出:**

```
Process done..
Objects are compressed.

```

> **对象压缩前:**
> [![](img/d1463604dd8463c74a9beb865792a2c1.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200701004706/beforecompress.PNG) 
> **对象压缩后:**
> [![](img/47aee99816ee17514629ebc76614ae4a.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200701004800/aftercompress.PNG)
> 
> 文件的大小可以压缩到初始大小的 70%。

### 优势

1.  大量对象可以通过网络传输，而不会出现任何性能问题。
2.  压缩-解压缩过程中不会丢失任何数据。

### 不足之处

1.  如果文件非常大，压缩和解压缩可能需要时间。