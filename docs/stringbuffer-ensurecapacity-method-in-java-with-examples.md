# Java 中的 StringBuffer ensureCapacity()方法，示例

> 原文:[https://www . geeksforgeeks . org/stringbuffer-ensurecapacity-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-ensurecapacity-method-in-java-with-examples/)

**StringBuffer 类**的**保证容量()**方法保证容量至少等于规定的最小容量。

*   如果 StringBuffer 的当前容量
*   如果最小容量参数>旧容量的两倍，加上 2，则新容量等于最小容量，否则新容量等于旧容量的两倍，加上 2。
*   如果作为参数< 0 传递的 minimumCapacity 参数，此方法不采取任何操作。

**语法:**

```
public void ensureCapacity(int minimumCapacity)
```

**参数:**该方法取一个参数**最小容量**，即最小期望容量。

**返回值:**这个方法返回不返回任何东西。

下面的程序演示了 StringBuffer 类的 ensureCapacity()方法

**例 1:**

```
// Java program to demonstrate
// the ensureCapacity() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        StringBuffer str = new StringBuffer();

        // print string capacity
        System.out.println("Before ensureCapacity "
                           + "method capacity = "
                           + str.capacity());

        // apply ensureCapacity()
        str.ensureCapacity(18);

        // print string capacity
        System.out.println("After ensureCapacity"
                           + " method capacity = "
                           + str.capacity());
    }
}
```

**Output:**

```
Before ensureCapacity method capacity = 16
After ensureCapacity method capacity = 34

```

**例 2:**

```
// Java program to demonstrate
// the ensureCapacity() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuffer object
        StringBuffer
            str
            = new StringBuffer("Geeks For Geeks");

        // print string capacity
        System.out.println("Before ensureCapacity "
                           + "method capacity = "
                           + str.capacity());

        // apply ensureCapacity()
        str.ensureCapacity(42);

        // print string capacity
        System.out.println("After ensureCapacity"
                           + " method capacity = "
                           + str.capacity());
    }
}
```

**Output:**

```
Before ensureCapacity method capacity = 31
After ensureCapacity method capacity = 64

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuffer . html # ensureCapacity(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuffer.html#ensureCapacity(int))