# Java 中的 ShortBuffer hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/short buffer-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/shortbuffer-hashcode-method-in-java-with-examples/)

**java.nio.ShortBuffer** 的 **hashCode()** 方法用于返回特定缓冲区的哈希代码。
短缓冲区的哈希代码只依赖于它的剩余元素；也就是说，从位置()到极限()1 的元素。
由于缓冲区哈希码依赖于内容，因此不建议将缓冲区用作哈希映射或类似数据结构中的密钥，除非知道它们的内容不会改变。

**语法**:

```java
public int hashCode()
```

**参数**:该方法不取任何参数。

**返回值**:该方法返回缓冲区的当前哈希码。

下面的程序说明了 **hashCode()** 方法的使用:

**程序 1** :

```java
// Java program to demonstrate
// compareTo() method
import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // create short object and assign value to it
        short shortNum1 = 150;
        Short ShortObj1 = new Short(shortNum1);

        // returns hashcode
        int hcode = ShortObj1.hashCode();
        System.out.println("Hashcode for this Short ShortObj1 = "
                           + hcode);
    }
}
```

**Output:**

```java
Hashcode for this Short ShortObj1 = 150

```

**程序 2** :

```java
// Java program to demonstrate
// compareTo() method
import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // create short object and assign value to it
        short shortNum1 = 6010;
        Short ShortObj1 = new Short(shortNum1);

        // returns hashcode
        int hcode = ShortObj1.hashCode();
        System.out.println("Hashcode for this Short ShortObj1 = "
                           + hcode);
    }
}
```

**Output:**

```java
Hashcode for this Short ShortObj1 = 6010

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/short buffer . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/nio/ShortBuffer.html#hashCode--)