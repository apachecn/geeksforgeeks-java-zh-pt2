# Java 中的 ShortBuffer toString()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-tostring-method-in-java-with-examples/)

**java.nio.ShortBuffer** 中的 **toString()** 方法用于返回一个总结该缓冲区状态的字符串。

**语法**:

```
public String toString()
```

**返回值**:该方法返回一个汇总字符串。

以下是说明 **toString()** 方法的示例:

**程序 1** :

```
// Java program to demonstrate
// toString() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating Shortbuffere
        ShortBuffer bb = ShortBuffer.allocate(100);
        bb.put((short)20);
        bb.put((short)30);
        // using toString method
        System.out.println(bb.toString());
    }
}
```

**Output:**

```
java.nio.HeapShortBuffer[pos=2 lim=100 cap=100]

```

**程序 2** :

```
// Java program to demonstrate
// toString() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating Shortbuffere
        ShortBuffer bb = ShortBuffer.allocate(300);
        bb.put((short)20);
        bb.put((short)30);
        bb.rewind();
        // using toString method
        System.out.println(bb.toString());
    }
}
```

**Output:**

```
java.nio.HeapShortBuffer[pos=0 lim=300 cap=300]

```