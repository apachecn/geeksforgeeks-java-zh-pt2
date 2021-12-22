# Java 中的 ShortBuffer compareTo 方法示例

> 原文:[https://www . geesforgeks . org/short buffer-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-compareto-method-in-java-with-examples/)

**java.nio.ShortBuffer** 类的 **compareTo()** 方法用于比较一个缓冲区和另一个缓冲区。

两个短缓冲区通过字典式比较它们的剩余元素序列来进行比较，而不考虑每个序列在其相应缓冲区内的起始位置。对短元素进行比较，就像调用 Short.compare(短，短)一样。短缓冲区无法与任何其他类型的对象相比。

**语法**:

```
public int compareTo(ShortBuffer that)
```

**参数**:该方法以一个**短缓冲区**对象作为参数，与该缓冲区进行比较。

**返回值**:该方法返回一个**负整数、零或一个正整数**，因为该缓冲区小于、等于或大于给定缓冲区的。

以下是举例说明 **compareTo()** 方法的例子:

**程序 1** :当两个浮动缓冲器相等时。

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the sb
        int capacity1 = 3;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer sb
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity1);

            // putting the value in sb
            sb.put((short)956);
            sb.put((short)761);
            sb.put((short)461);

            // revind the short buffer
            sb.rewind();

            // print the ShortBuffer
            System.out.println(" ShortBuffer sb: "
                               + Arrays.toString(sb.array()));

            // creating object of shortbuffer sb1
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity1);

            // putting the value in sb1
            sb1.put((short)956);
            sb1.put((short)761);
            sb1.put((short)461);

            // revind the short buffer
            sb1.rewind();

            // print the shortBuffer
            System.out.println(" ShortBuffer sb1: "
                               + Arrays.toString(sb1.array()));

            // compare both buffer and store the value into integer
            int i = sb.compareTo(sb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal ");
            else if (i >= 0)
                System.out.println("\nfb is lexicographically greater than fb1 ");
            else
                System.out.println("\nfb is lexicographically less than fb1 ");
        }

        catch (IllegalArgumentException e) {
            System.out.println(" Exception throws: "
                               + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println(" Exception throws: "
                               + e);
        }
    }
}
```

**Output:**

```
ShortBuffer sb: [956, 761, 461]
ShortBuffer sb1: [956, 761, 461]

both buffer are lexicographically equal

```

**程序 2** :当这个短缓冲区大于传递的短缓冲区时

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the sb
        int capacity1 = 3;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer sb
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity1);

            // putting the value in sb
            sb.put((short)956);
            sb.put((short)761);
            sb.put((short)41);

            // revind the short buffer
            sb.rewind();

            // print the ShortBuffer
            System.out.println(" ShortBuffer s: "
                               + Arrays.toString(sb.array()));

            // creating object of shortbuffer sb1
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity1);

            // putting the value in sb1
            sb1.put((short)856);
            sb1.put((short)761);
            sb1.put((short)461);

            // revind the short buffer
            sb1.rewind();

            // print the ShortBuffer
            System.out.println(" ShortBuffer sb1: "
                               + Arrays.toString(sb1.array()));

            // compare both buffer and store the value into integer
            int i = sb.compareTo(sb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal ");
            else if (i >= 0)
                System.out.println("\nfb is lexicographically greater than fb1 ");
            else
                System.out.println("\nfb is lexicographically less than fb1 ");
        }

        catch (IllegalArgumentException e) {
            System.out.println(" Exception throws: "
                               + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println(" Exception throws: "
                               + e);
        }
    }
}
```

**Output:**

```
ShortBuffer s: [956, 761, 41]
ShortBuffer sb1: [856, 761, 461]

fb is lexicographically greater than fb1

```

**程序 3** :当这个短缓存小于传递的短缓存时

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the sb
        int capacity1 = 3;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer sb
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity1);

            // putting the value in sb
            sb.put((short)856);
            sb.put((short)761);
            sb.put((short)461);

            // revind the short buffer
            sb.rewind();

            // print the ShortBuffer
            System.out.println(" ShortBuffer sb: "
                               + Arrays.toString(sb.array()));

            // creating object of shortbuffer sb1
            // and allocating size capacity
            ShortBuffer sb1 = ShortBuffer.allocate(capacity1);

            // putting the value in sb1
            sb1.put((short)956);
            sb1.put((short)761);
            sb1.put((short)461);

            // revind the short buffer
            sb1.rewind();

            // print the ShortBuffer
            System.out.println(" ShortBuffer sb1: "
                               + Arrays.toString(sb1.array()));

            // compare both buffer and store the value into integer
            int i = sb.compareTo(sb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal ");
            else if (i >= 0)
                System.out.println("\nfb is lexicographically greater than fb1 ");
            else
                System.out.println("\nfb is lexicographically less than fb1 ");
        }

        catch (IllegalArgumentException e) {
            System.out.println(" Exception throws: "
                               + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println(" Exception throws: "
                               + e);
        }
    }
}
```

**Output:**

```
ShortBuffer sb: [856, 761, 461]
ShortBuffer sb1: [956, 761, 461]

fb is lexicographically less than fb1

```