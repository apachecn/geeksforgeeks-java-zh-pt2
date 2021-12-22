# Java 中的 ShortBuffer allocate()方法示例

> 原文:[https://www . geesforgeks . org/short buffer-allocate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-allocate-method-in-java-with-examples/)

**java.nio.ShortBuffer** 类的 **allocate()** 方法用于分配一个新的短缓冲区。
新缓冲区的位置将为零&它的极限是它的容量，尽管标记是未定义的，并且它的每个元素都被初始化为零。它将有一个后备数组，数组偏移量为零。
**语法** :

```
public static ShortBuffer allocate(int capacity)
```

**参数**:该方法接受一个强制参数**容量**，该参数指定了新缓冲器的容量，以短路形式表示。
**返回值**:此方法返回新的**短缓冲**。
**异常**:如果容量为负整数，该方法抛出**IllegalArgumentException**。
下面的程序说明了 **allocate()** 方法的使用:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 5;

        // Creating the ShortBuffer

        // creating object of Shortbuffer
        // and allocating size capacity
        ShortBuffer sb = ShortBuffer.allocate(capacity);

        // putting the value in Shortbuffer
        sb.put((short)10000);
        sb.put((short)10640);
        sb.put((short)10189);
        sb.put((short)-2000);
        sb.put((short)-16780);

        // Printing the ShortBuffer
        System.out.println("ShortBuffer: "
                           + Arrays.toString(sb.array()));
    }
}
```

**Output:** 

```
ShortBuffer: [10000, 10640, 10189, -2000, -16780]
```

**程序 2:** 显示空指针异常

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        // by negative integer
        int capacity = -10;

        // Creating the ShortBuffer
        try {

            // creating object of shortbuffer
            // and allocating size with negative integer
            System.out.println("Trying to allocate a negative integer");

            FloatBuffer fb = FloatBuffer.allocate(capacity);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```
Trying to allocate a negative integer
Exception thrown: java.lang.IllegalArgumentException: capacity < 0: (-10 < 0)

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/nio/short buffer . html # allocate()T4】