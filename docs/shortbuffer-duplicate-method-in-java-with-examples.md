# Java 中的 ShortBuffer 重复()方法，示例

> 原文:[https://www . geeksforgeeks . org/short buffer-用示例复制 java 中的方法/](https://www.geeksforgeeks.org/shortbuffer-duplicate-method-in-java-with-examples/)

**java.nio.ShortBuffer** 类的**replicate()**方法创建一个共享该缓冲区内容的新的短缓冲区。

新缓冲区的内容将是该缓冲区的内容。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法**:

```
public abstract ShortBuffer duplicate()
```

**返回值**:该方法返回**新的短缓冲区**。

下面的程序说明了**复制()**的方法:

**程序 1** :

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Declaring the capacity of the sb
        int capacity1 = 10;
        // Creating the ShortBuffer

        // creating object of shortbuffer sb
        // and allocating size capacity
        ShortBuffer sb1 = ShortBuffer.allocate(capacity1);

        // putting the value in sb
        sb1.put((short)100);
        sb1.put((short)400);
        sb1.put((short)210);

        // revind the short buffer
        sb1.rewind();

        // print the Original ShortBuffer
        System.out.println("Original ShortBuffer:  "
                           + Arrays.toString(sb1.array()));

        // creating duplicate
        ShortBuffer sb2 = sb1.duplicate();

        // print the duplicate copy of ShortBuffer
        System.out.println("Duplicate ShortBuffer: "
                           + Arrays.toString(sb2.array()));

        // checking if the duplicate is correct or not
        System.out.println("are sb1 and sb2 equal: "
                           + sb1.equals(sb2));
    }
}
```

**Output:**

```
Original ShortBuffer:  [100, 400, 210, 0, 0, 0, 0, 0, 0, 0]
Duplicate ShortBuffer: [100, 400, 210, 0, 0, 0, 0, 0, 0, 0]
are sb1 and sb2 equal: true

```

**程序 2** :

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the sb
        int capacity1 = 10;

        // Creating the ShortBuffer

        // creating object of shortbuffer sb
        // and allocating size capacity
        ShortBuffer sb1 = ShortBuffer.allocate(capacity1);
        ShortBuffer sb3 = ShortBuffer.allocate(capacity1);

        // putting the value in sb
        sb1.put((short)100);
        sb1.put((short)400);
        sb1.put((short)210);

        // revind the short buffer
        sb1.rewind();

        // print the Original ShortBuffer
        System.out.println("Original ShortBuffer:  "
                           + Arrays.toString(sb1.array()));

        // creating duplicate
        ShortBuffer sb2 = sb1.duplicate();

        // print the duplicate copy of ShortBuffer
        System.out.println("Duplicate ShortBuffer: "
                           + Arrays.toString(sb2.array()));

        // checking if the duplicate is correct or not
        System.out.println("are sb1 and sb2 equal: "
                           + sb1.equals(sb2));

        // checking if the duplicate is correct or not
        System.out.println("are sb2 and sb3 equal: "
                           + sb2.equals(sb3));
    }
}
```

**Output:**

```
Original ShortBuffer:  [100, 400, 210, 0, 0, 0, 0, 0, 0, 0]
Duplicate ShortBuffer: [100, 400, 210, 0, 0, 0, 0, 0, 0, 0]
are sb1 and sb2 equal: true
are sb2 and sb3 equal: false

```