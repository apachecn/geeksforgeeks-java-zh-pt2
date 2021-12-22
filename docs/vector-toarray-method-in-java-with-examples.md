# Java 中的向量到数组()方法，示例

> 原文:[https://www . geesforgeks . org/vector-to array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/vector-toarray-method-in-java-with-examples/)

### 1 . toarray()

Java 中 [Vector 类](https://www.geeksforgeeks.org/java-util-vector-class-java/)的 **toArray()** 方法用于形成一个与 Vector 相同元素的数组。基本上，它将向量中的所有元素复制到一个新数组中。

**语法:**

```java
Object[] arr = Vector.toArray()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个包含类似于向量的元素的数组。

下面的程序说明了 Vector.toArray()方法:

**程序 1:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("For");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("The Vector: " + vec_tor);

        // Creating the array and using toArray()
        Object[] arr = vec_tor.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Vector: [Welcome, To, Geeks, For, Geeks]
The array is:
Welcome
To
Geeks
For
Geeks

```

**程序 2:**

```java
// Java code to illustrate toArray()

import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<Integer> vec_tor = new Vector<Integer>();

        // Use add() method to add elements into the Vector
        vec_tor.add(10);
        vec_tor.add(15);
        vec_tor.add(30);
        vec_tor.add(20);
        vec_tor.add(5);
        vec_tor.add(25);

        // Displaying the Vector
        System.out.println("The Vector: " + vec_tor);

        // Creating the array and using toArray()
        Object[] arr = vec_tor.toArray();

        System.out.println("The array is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Vector: [10, 15, 30, 20, 5, 25]
The array is:
10
15
30
20
5
25

```

### 2 . toaarray(arr[])

Java 中[向量类](https://www.geeksforgeeks.org/java-util-vector-class-java/)的 **toArray(arr[])** 方法方法用于形成与向量相同元素的数组。它以正确的顺序返回一个包含该向量中所有元素的数组**；**返回数组的运行时类型是指定数组的运行时类型。如果向量适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和该向量的大小来分配新数组。
如果向量适合指定的数组，并且有空间可以备用(即数组中的元素比向量多)，数组中紧接向量末尾的元素将被设置为空。(只有当调用者知道向量不包含任何空元素时，这在确定向量的长度时才有用。)

**语法:**

```java
Object[] arr1 = Vector.toArray(arr[])
```

**参数:**该方法接受一个参数 **arr[]** ，如果向量足够大，则该参数是向量元素要存储到的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该方法返回一个包含类似于向量的元素的数组。

**异常:**该方法可能会引发两种类型的异常:

*   **arraystorexception**:当提到的数组是不同类型的，无法与向量中提到的元素进行比较时。
*   **NullPointerException** :如果数组为 Null，那么抛出这个异常。

下面的程序说明了 Vector.toArray(arr[])方法的工作原理。

**程序 1:** 当数组的大小为向量时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("For");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("The Vector: " + vec_tor);

        // Creating the array and using toArray()
        String[] arr = new String[5];
        arr = vec_tor.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Vector: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks

```

**程序 2:** 当数组小于向量的大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("For");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("The Vector: " + vec_tor);

        // Creating the array and using toArray()
        String[] arr = new String[1];
        arr = vec_tor.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Vector: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks

```

**程序 3:** 当数组大于向量大小时

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("For");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("The Vector: " + vec_tor);

        // Creating the array and using toArray()
        String[] arr = new String[10];
        arr = vec_tor.toArray(arr);

        // Displaying arr
        System.out.println("The arr[] is:");
        for (int j = 0; j < arr.length; j++)
            System.out.println(arr[j]);
    }
}
```

**Output:**

```java
The Vector: [Welcome, To, Geeks, For, Geeks]
The arr[] is:
Welcome
To
Geeks
For
Geeks
null
null
null
null
null

```

**程序 4:** 演示空指针异常

```java
// Java code to illustrate toArray(arr[])

import java.util.*;

public class VectorDemo {
    public static void main(String args[])
    {
        // Creating an empty Vector
        Vector<String> vec_tor = new Vector<String>();

        // Use add() method to add elements into the Vector
        vec_tor.add("Welcome");
        vec_tor.add("To");
        vec_tor.add("Geeks");
        vec_tor.add("For");
        vec_tor.add("Geeks");

        // Displaying the Vector
        System.out.println("The Vector: " + vec_tor);

        try {
            // Creating the array
            String[] arr = null;
            // using toArray()
            // Since arr is null
            // Hence exception will be thrown
            arr = vec_tor.toArray(arr);

            // Displaying arr
            System.out.println("The arr[] is:");
            for (int j = 0; j < arr.length; j++)
                System.out.println(arr[j]);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
The Vector: [Welcome, To, Geeks, For, Geeks]
Exception: java.lang.NullPointerException

```