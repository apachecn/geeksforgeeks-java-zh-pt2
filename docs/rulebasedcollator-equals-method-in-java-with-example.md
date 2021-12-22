# Java 中的 RuleBasedCollator equals()方法，示例

> 原文:[https://www . geesforgeks . org/rulesbasedcollator-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/rulebasedcollator-equals-method-in-java-with-example/)

**java.text.Collator 类**的 **equals()** 方法用于检查两个指定的字符串是否相同。

**语法:**

```
public boolean equals(String source,
                      String target)
```

**参数**:该方法取两个**字符串**，在这两个字符串之间进行比较。
**返回值:**如果两个字符串相等，则返回**真**否则返回**假**。
以下举例说明**等于()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator("< a< b< c< d");

            // Creating an initializing
            // object for comparison
            String obj1 = "a";

            // Creating an initializing
            // Object for comparison
            String obj2 = "A";

            // compare both object
            // using equals() method
            boolean i = col.equals(obj1, obj2);

            // display result
            if (i)
                System.out.println(obj1
                                   + " is equal to "
                                   + obj2);
            else
                System.out.println(obj1
                                   + " is not equal to "
                                   + obj2);
        }

        catch (ParseException e) {

            System.out.println(e);
        }
    }
}
```

**Output:** 

```
a is not equal to A
```