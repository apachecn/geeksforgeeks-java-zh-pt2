# 解析 Java 中的 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/parse position-hashcode-method-in-Java-with-example/](https://www.geeksforgeeks.org/parseposition-hashcode-method-in-java-with-example/)

类的 **hashCode()** 方法用于检索当前解析位置对象的 hash 代码。

**语法:**

```java
public int hashCode()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回当前解析位置对象的**哈希代码**。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos
                = new ParsePosition(500);

            // getting hashCode for
            // current ParsePosition Object
            // using getIndex() method
            int i = pos.hashCode();

            // display result
            System.out.println(
                "hashCode: "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```java
hashCode: -65036

```

**例 2:**

```java
// Java program to demonstrate
// hashCode() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos
                = new ParsePosition(-1);

            // getting hashCode for
            // current ParsePosition Object
            // using getIndex() method
            int i = pos.hashCode();

            // display result
            System.out.println(
                "hashCode: "
                + Integer.toString(i));
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```java
hashCode: -1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/parseposition . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/text/ParsePosition.html#hashCode--)