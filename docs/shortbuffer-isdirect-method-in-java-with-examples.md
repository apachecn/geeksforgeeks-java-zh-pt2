# Java 中的 ShortBuffer isDirect()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-is direct-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-isdirect-method-in-java-with-examples/)

**[Java . nio . short buffer](https://www.geeksforgeeks.org/tag/java-shortbuffer/)**的 **isDirect()** 方法用于检查这个短缓冲是否是直接的。

**语法** :

```
public abstract boolean isDirect()
```

**返回值**:当且仅当该缓冲区为直接时，该方法返回**真**

以下程序说明了 **isDirect()** 方法的使用:

**程序 1** :

```
// Java program to demonstrate
// isDirect() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        short[] array = { 10000, 10640, 10189, -2000, -16780 };

        // creating short array
        ShortBuffer shortBuf1 = ShortBuffer.wrap(array);

        // checking if the array is Direct or not
        if (shortBuf1.isDirect()) {
            System.out.println("Short buffer is direct.");
        }
        else {
            System.out.println("Short buffer is not direct.");
        }
    }
}
```

**输出:**

```
Short buffer is not direct.

```

**程序二** :

```
// Java program to demonstrate
// isDirect() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        ByteBuffer b = ByteBuffer.allocateDirect(512);

        ShortBuffer shortBuf = b.asShortBuffer();

        // checking if the array is Direct or not
        if (shortBuf.isDirect()) {
            System.out.println("Short buffer is direct.");
        }
        else {
            System.out.println("Short buffer is not direct.");
        }
    }
}
```

**输出:**

```
Short buffer is direct.

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # isDirect–](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#isDirect--)