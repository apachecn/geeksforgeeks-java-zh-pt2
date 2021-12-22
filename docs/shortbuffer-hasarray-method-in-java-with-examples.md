# Java 中的 ShortBuffer hasArray()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-hasarray-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-hasarray-method-in-java-with-examples/)

**java.nio.ShortBuffer** 类的 **hasArray()** 方法用于确保给定的缓冲区是否由可访问的浮点数组支持。如果该缓冲区有可访问的后备数组，则返回 true，否则返回 false。如果此方法返回 true，则可以安全地调用 array()和 arrayOffset()方法，因为它们在支持数组上工作。

**语法**:

```java
public final boolean hasArray()
```

**返回**:当且仅当该缓冲区由数组支持且不是只读时，该方法将返回**真**。否则返回假。

以下是说明 **hasArray()** 方法的例子:

**程序 1** :
当缓冲区由数组支持时。

```java
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity);

            // putting the value in Shortbuffer
            sb.put((short)256);
            sb.put(2, (short)91);
            sb.rewind();

            // checking ShortBuffer sb is backed by array or not
            boolean isArray = sb.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("ShortBuffer sb is"
                                   + " backed by array");
            else
                System.out.println("ShortBuffer sb is"
                                   + " not backed by any array");
        }

        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output:**

```java
ShortBuffer sb is backed by array

```

**程序 2** :
当缓冲区没有数组支持时。

```java
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity);

            // putting the value in Shortbuffer
            sb.put((short)856);
            sb.put(2, (short)961);
            sb.rewind();

            // Creating a read-only copy of ShortBuffer
            // using asReadOnlyBuffer() method
            ShortBuffer sb1 = sb.asReadOnlyBuffer();

            // checking ShortBuffer sb is backed by array or not
            boolean isArray = sb1.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("ShortBuffer sb is"
                                   + " backed by array");
            else
                System.out.println("ShortBuffer sb is"
                                   + " not backed by any array");
        }

        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output:**

```java
ShortBuffer sb is not backed by any array

```