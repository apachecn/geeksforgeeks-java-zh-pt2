# Java 中的规则库克隆()方法，示例

> 原文:[https://www . geesforgeks . org/rulesbasedcollator-clone-method-in-Java-with-example/](https://www.geeksforgeeks.org/rulebasedcollator-clone-method-in-java-with-example/)

**Java . text . rulesbasedcollator**类的 **clone()** 方法用于获取这个 Collator 对象的副本。

**语法:**

```java
public Object clone()
```

**参数**:此方法不接受任何参数。

**返回值:**这个方法返回这个 Collator 对象的副本。

以下是说明**克隆()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// clone() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initalizing new simple rule
            String simple = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting copy of this object
            // using clone() mehtod
            Object obj = col.clone();

            // display result
            System.out.println("equivalent object :- "
                               + obj);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出:**

```java
equivalent object :- java.text.RuleBasedCollator@7033e09a

```

**例 2:**

```java
// Java program to demonstrate
// clone() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initalizing new simple rule
            String simple = "< a < c & a < b";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting copy of this object
            // using clone() mehtod
            Object obj = col.clone();

            // display result
            System.out.println("equivalent object :- "
                               + obj);
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : "
                               + e);
        }
    }
}
```

**输出:**

```java
equivalent object :- java.text.RuleBasedCollator@78930901

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/rulesbasedcollator . html # clone–](https://docs.oracle.com/javase/9/docs/api/java/text/RuleBasedCollator.html#clone--)