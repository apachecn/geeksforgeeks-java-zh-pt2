# Java 中的 rulesbasedcollator getcollectionkey()方法，示例

> 原文:[https://www . geesforgeks . org/rulesbasedcollator-getcollationkey-method-in-Java-with-example/](https://www.geeksforgeeks.org/rulebasedcollator-getcollationkey-method-in-java-with-example/)

**Java . text . rulesbasedcollator 类**的 **getCollationKey()** 方法用于获取从传入的字符串转换而来的位序列。
**语法:**

```
public CollationKey getCollationKey(String source)
```

**参数**:该方法接受**字符串对象**作为参数。
**返回值:**该方法返回从传递给它的字符串转换而来的一系列位。
以下是举例说明 **getCollationKey()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getCollationKey() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new simple rule
            String simple
                = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting sereis of bits
            // using getCollationKey() method
            CollationKey key
                = col.getCollationKey("Geek");

            // display result
            System.out.println(
                "Series of bits are :- "
                + key.getSourceString());
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Series of bits are :- Geek
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getCollationKey() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing
            // new simple rule
            String simple
                = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting sereis of bits
            // using getCollationKey() method
            CollationKey key
                = col.getCollationKey("G_f_G");

            // display result
            System.out.println(
                "Series of bits are :- "
                + key.getSourceString());
        }

        catch (ClassCastException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ParseException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
Series of bits are :- G_f_G
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/rulesbasedcollator . html # getCollationKey-Java . lang . string-T4】