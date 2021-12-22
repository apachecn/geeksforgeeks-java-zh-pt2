# Java 中的 ShortBuffer order()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-order-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-order-method-in-java-with-examples/)

**java.nio.ShortBuffer** 的 **order()** 方法用于检索缓冲区的字节顺序。
通过分配或包装现有短数组创建的短缓冲区的字节顺序是底层硬件的本机顺序。作为字节缓冲区视图创建的短缓冲区的字节顺序是创建视图时字节缓冲区的字节顺序。

**语法**:

```
public abstract ByteOrder order()
```

**返回值**:该方法返回**缓冲区的字节顺序。**

以下程序说明了**顺序()**方法的使用:

**程序 1** :

```
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // creating short buffer
        ShortBuffer bb = ShortBuffer.allocate(7);

        bb.put((short)44);

        // using the order method
        System.out.println(bb.order());
    }
}
```

**Output:**

```
LITTLE_ENDIAN

```