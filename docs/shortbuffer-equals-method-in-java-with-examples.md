# Java 中的 ShortBuffer equals()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-equals-method-in-java-with-examples/)

**java.nio.ShortBuffer** 类的 **equals()** 方法用于检查给定的缓冲区是否等于另一个对象。

当且仅当两个短缓冲区相等时，

*   它们具有相同的元素类型，
*   它们具有相同数量的剩余元素，并且
*   剩余元素的两个序列，独立于它们的起始位置，是逐点相等的
    。

短缓冲区不等于任何其他类型的对象。

**语法**:

```
public boolean equals(Object ob)
```

**参数**:该方法以该缓冲区要比较的对象 **ob** 为参数。

**返回值**:当且仅当该缓冲区等于给定对象时，该方法返回**真**。

以下是说明**等于()**方法的示例:

**程序 1** :

```
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the ShortBuffer 2
        int capacity2 = 10;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer 1
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity1);

            // creating object of Shortbuffer 2
            // and allocating size capacity
            ShortBuffer fb2 = ShortBuffer.allocate(capacity2);

            // putting the value in Shortbuffer 1
            sb1.put((short)856);
            sb1.put(2, (short)961);
            sb1.rewind();

            // putting the value in Shortbuffer 2
            fb2.put((short)856);
            fb2.put(2, (short)961);
            fb2.rewind();

            // print the ShortBuffer 1
            System.out.println(" ShortBuffer 1: "
                               + Arrays.toString(sb1.array()));

            // print the ShortBuffer 2
            System.out.println(" ShortBuffer 2: "
                               + Arrays.toString(fb2.array()));

            // checking the equality of both ShortBuffer
            boolean fbb = sb1.equals(fb2);

            // checking if else condition
            if (fbb)
                System.out.println("both are equal");
            else
                System.out.println("both are not equal");
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

```
ShortBuffer 1: [856, 0, 961, 0, 0, 0, 0, 0, 0, 0]
ShortBuffer 2: [856, 0, 961, 0, 0, 0, 0, 0, 0, 0]

both are equal

```

**程序 2** :

```
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the ShortBuffer 2
        int capacity2 = 5;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer 1
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity1);

            // creating object of Shortbuffer 2
            // and allocating size capacity
            ShortBuffer sb2 = ShortBuffer.allocate(capacity2);

            // putting the value in Shortbuffer 1
            sb1.put((short)856);
            sb1.put(2, (short)961);
            sb1.rewind();

            // putting the value in Shortbuffer 2
            sb2.put((short)856);
            sb2.put(2, (short)431);
            sb2.rewind();

            // print the ShortBuffer 1
            System.out.println(" ShortBuffer 1: "
                               + Arrays.toString(sb1.array()));

            // print the ShortBuffer 2
            System.out.println(" ShortBuffer 2: "
                               + Arrays.toString(sb2.array()));

            // checking the equality of both ShortBuffer
            boolean fbb = sb1.equals(sb2);

            // checking if else condition
            if (fbb)
                System.out.println("both are equal");
            else
                System.out.println("both are not equal");
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

```
ShortBuffer 1: [856, 0, 961, 0, 0, 0, 0, 0, 0, 0]
ShortBuffer 2: [856, 0, 431, 0, 0]

both are not equal

```