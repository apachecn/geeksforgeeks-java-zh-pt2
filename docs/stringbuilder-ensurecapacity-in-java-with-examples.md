# Java 中的 StringBuilder ensureCapacity()示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-ensurecapacity-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-ensurecapacity-in-java-with-examples/)

**字符串构建器类**的**确保容量(int minimumCapacity)** 方法帮助我们确保容量至少等于作为参数传递给该方法的指定的 minimumCapacity。

*   如果 StringBuilder 的当前容量小于参数 minimumCapacity，则分配一个容量更大的新内部数组。
*   如果最小容量参数大于旧容量的两倍，加上 2，则新容量等于最小容量，否则新容量等于旧容量的两倍，加上 2。
*   如果作为参数传递的 minimumCapacity 参数不是-正数，则此方法不采取任何操作。

**语法:**

```java
public void ensureCapacity(int minimumCapacity)
```

**参数:**该方法接受一个参数**最小容量**代表你想要的最小期望容量。

**返回值:**这个方法不返回任何东西。

下面的程序演示了 StringBuilder 类的 ensureCapacity()方法:

**例 1:**

在本程序中，等于 18 的最小容量参数小于旧容量的两倍，加上等于 34 的 2，则新容量等于 34。

```java
// Java program to demonstrate
// the ensureCapacity() Method.

class GFG {
    public static void main(String[] args)
    {
        // create a StringBuilder object
        StringBuilder str = new StringBuilder();

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

**输出:**

```java
Before ensureCapacity method capacity = 16
After ensureCapacity method capacity = 34

```

**例 2:**

在本程序中，等于 44 的最小容量参数大于旧容量的两倍，加上等于 34 的 2，则新容量等于 34。

```java
// Java program to demonstrate
// the ensureCapacity() Method.

class GFG {
    public static void main(String[] args)
    {

        // create a StringBuilder object
        StringBuilder str = new StringBuilder();

        // print string capacity
        System.out.println("Before ensureCapacity"
                           + " method capacity = "
                           + str.capacity());

        // apply ensureCapacity()
        str.ensureCapacity(44);

        // print string capacity
        System.out.println("After ensureCapacity"
                           + " method capacity = "
                           + str.capacity());
    }
}
```

**输出:**

```java
Before ensureCapacity method capacity = 16
After ensureCapacity method capacity = 44

```

**参考:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/stringbuilder . html # ensureCapacity(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/StringBuilder.html#ensureCapacity(int))