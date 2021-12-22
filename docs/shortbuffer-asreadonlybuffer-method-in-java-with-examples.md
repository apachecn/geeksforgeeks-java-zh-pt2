# Java 中的 ShortBuffer asReadOnlyBuffer()方法，示例

> 原文:[https://www . geesforgeks . org/short buffer-as readonly buffer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/shortbuffer-asreadonlybuffer-method-in-java-with-examples/)

类的 **asReadOnlyBuffer()** 方法用于用这个缓冲区的内容创建一个新的只读短缓冲区。新缓冲区是该缓冲区的副本。因此，对此缓冲区内容所做的更改将在新缓冲区中可见。

由于新缓冲区是只读的，因此不允许对其内容进行任何修改。两个缓冲器的位置、极限和标记值将是独立的。新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果此缓冲区本身是只读的，则此方法的行为方式与复制方法完全相同。

**语法**:

```
public abstract ShortBuffer asReadOnlyBuffer()
```

**返回值**:该方法返回新的、**只读短缓冲区**，内容与该缓冲区相同。

以下是举例说明**作为 ReadOnlyBuffer()** 方法的例子:

**程序 1** :

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity);

            // putting the value in shortbuffer
            sb.put((short)856);
            sb.put(2, (short)961);
            sb.rewind();

            // print the ShortBuffer
            System.out.println("Original ShortBuffer: "
                               + Arrays.toString(sb.array()));

            // Creating a read-only copy of ShortBuffer
            // using asReadOnlyBuffer() method
            ShortBuffer shortBuffer = sb.asReadOnlyBuffer();

            // print the ShortBuffer
            System.out.print("\nReadOnlyBuffer ShortBuffer: ");

            while (shortBuffer.hasRemaining())
                System.out.print(shortBuffer.get() + ", ");
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
Original ShortBuffer: [856, 0, 961, 0, 0, 0, 0, 0, 0, 0]

ReadOnlyBuffer ShortBuffer: 856, 0, 961, 0, 0, 0, 0, 0, 0, 0,

```

**程序 2** :

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args) throws Exception
    {

        // Declaring the capacity of the sb
        int capacity1 = 10;

        // Declaring the capacity of the sb1
        int capacity2 = 5;

        // Creating the ShortBuffer
        try {

            //
            // sb
            //
            // creating object of shortbuffer sb
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity1);

            // putting the value in sb
            sb.put((short)856);
            sb.put(2, (short)961);
            sb.rewind();

            // print the ShortBuffer
            System.out.println("ShortBuffer sb: "
                               + Arrays.toString(sb.array()));

            //
            // sb1
            //
            // creating object of shortbuffer sb1
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity2);

            // putting the value in sb1
            sb1.put(1, (short)456);
            sb1.put(2, (short)645);
            sb1.rewind();

            // print the ShortBuffer
            System.out.println("\nShortBuffer sb1: "
                               + Arrays.toString(sb1.array()));

            // Creating a read-only copy of ShortBuffer
            // using asReadOnlyBuffer() method
            ShortBuffer readOnlySb = sb.asReadOnlyBuffer();

            // print the ShortBuffer
            System.out.print("\nReadOnlyBuffer FloatBuffer: ");

            while (readOnlySb.hasRemaining())
                System.out.print(readOnlySb.get() + ", ");

            // try to change readOnlySb
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlyFb for editing");

            short[] sbarr = readOnlySb.array();
        }
        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }
        catch (ReadOnlyBufferException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```
ShortBuffer sb: [856, 0, 961, 0, 0, 0, 0, 0, 0, 0]

ShortBuffer sb1: [0, 456, 645, 0, 0]

ReadOnlyBuffer FloatBuffer: 856, 0, 961, 0, 0, 0, 0, 0, 0, 0, 

Trying to get the array from ReadOnlyFb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```