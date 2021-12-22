# Java 中的 rulesbasedcollator getcollectionelementiterator(字符串)方法

> 原文:[https://www . geeksforgeeks . org/rulesbasedcollator-getcollectionelementiteratorstring-method-in-Java/](https://www.geeksforgeeks.org/rulebasedcollator-getcollationelementiteratorstring-method-in-java/)

**Java . text . rulesbasedcollator 类**的**getcollectionelementiterator()**方法用于获取给定字符串的归类元素迭代器的对象。

**语法:**

```java
public CollationElementIterator
       getCollationElementIterator(String source)

```

**参数**:该方法接受**字符串对象**作为参数。

**返回值:**这个方法返回给定字符串的排序元素迭代器的对象。

以下是说明**getcollectionlementiterator()**方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getCollationElementIterator() method

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

            // Creating and initializing
            // the String Object
            String str = "ABABCC";

            // getting CollationElementIterator Object
            // for the given String
            // using getCollationElementIterator() method
            CollationElementIterator key
                = col.getCollationElementIterator(str);

            // display result
            System.out.println("CollationElementIterator is : "
                               + key);
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

**输出:**

```java
CollationElementIterator is : java.text.CollationElementIterator@7d4991ad

```

**例 2:**

```java
// Java program to demonstrate
// getCollationElementIterator() method

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
                = "< a < b & a < c";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // Creating and initializing the String Object
            String str = "GEeks";

            // getting CollationElementIterator Object
            // for the given String
            // using getCollationElementIterator() mehtod
            CollationElementIterator key
                = col.getCollationElementIterator(str);

            // display result
            System.out.println("CollationElementIterator is : "
                               + key);
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

**输出:**

```java
CollationElementIterator is : java.text.CollationElementIterator@7d4991ad

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/rulesbasedcollator . html # getcollateionelementiterator-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/text/RuleBasedCollator.html#getCollationElementIterator-java.lang.String-)