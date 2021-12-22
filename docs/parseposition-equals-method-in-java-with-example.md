# 解析位置等于()方法在 Java 中的示例

> 原文:[https://www . geeksforgeeks . org/parse position-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/parseposition-equals-method-in-java-with-example/)

**java.text.ParsePosition** 类的 **equals()** 方法用于检查两个 ParsePosition 对象是否相同。

**语法:**

```
public boolean equals(Object obj)
```

**参数**:该方法取 **ParsePosition** 对象，与当前 ParsePosition 对象进行比较。

**返回值:**如果两个**解析位置对象**彼此相等，则返回真，否则返回假。

以下是说明**等于()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// equals() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos_1
                = new ParsePosition(0);

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos_2
                = new ParsePosition(0);

            // compare both object
            // using equals() mehtod
            boolean i = pos_1.equals(pos_2);

            // display result
            if (i)
                System.out.println(
                    "pos_1 is equals to pos_2");
            else
                System.out.println(
                    "pos_1 is not equal to pos_2");
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```
pos_1 is equals to pos_2

```

**例 2:**

```
// Java program to demonstrate
// equals() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos_1
                = new ParsePosition(0);

            // Creating and initializing
            // new ParsePosition Object
            ParsePosition pos_2
                = new ParsePosition(1);

            // compare both object
            // using equals() mehtod
            boolean i = pos_1.equals(pos_2);

            // display result
            if (i)
                System.out.println(
                    "pos_1 is equals to pos_2");
            else
                System.out.println(
                    "pos_1 is not equal to pos_2");
        }

        catch (ClassCastException e) {

            System.out.println(e);
        }
    }
}
```

**输出:**

```
pos_1 is not equal to pos_2

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/parseposition . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/text/ParsePosition.html#equals-java.lang.Object-)