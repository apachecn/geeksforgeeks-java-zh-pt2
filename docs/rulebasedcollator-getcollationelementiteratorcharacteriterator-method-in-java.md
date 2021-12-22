# Java 中的 rulesbasedcollator getcollectionlementiterator(特性生成器)方法

> 原文:[https://www . geeksforgeeks . org/rulesbasedcollator-getcollationelementiteratorcharteriterator-method-in-Java/](https://www.geeksforgeeks.org/rulebasedcollator-getcollationelementiteratorcharacteriterator-method-in-java/)

**Java . text . rulesbasedcollator 类**的**getcollectionelementiterator()**方法用于获取给定字符迭代器对象的归类元素迭代器对象。

**语法:**

```
public CollationElementIterator getCollationElementIterator(CharacterIterator source)
```

**参数**:该方法接受**字符迭代器对象**作为参数。

**返回值:**这个方法返回给定字符串的排序元素迭代器的对象。

以下是说明**getcollectionlementiterator()**方法的示例:

**例 1:**

```
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
            // StringCharacterIterator Object
            StringCharacterIterator obj
                = new StringCharacterIterator("Geeks");

            // getting CollationElementIterator Object
            // for the given String
            // using getCollationElementIterator() method
            CollationElementIterator key
                = col.getCollationElementIterator(obj);

            // display result
            System.out.println(
                "CollationElementIterator is : "
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

```
CollationElementIterator is : java.text.CollationElementIterator@7d4991ad

```

**例 2:**

```
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

            // Creating and initializing
            // StringCharacterIterator Object
            StringCharacterIterator obj
                = new StringCharacterIterator("ABCDEF");

            // getting CollationElementIterator Object
            // for the given StringCharacterIterator Object
            // using getCollationElementIterator() method
            CollationElementIterator key
                = col.getCollationElementIterator(obj);

            // display result
            System.out.println(
                "CollationElementIterator is : "
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

```
CollationElementIterator is : java.text.CollationElementIterator@7d4991ad

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/rulesbasedcollator . html # getcollateionelementiterator-Java . text . terminator-](https://docs.oracle.com/javase/9/docs/api/java/text/RuleBasedCollator.html#getCollationElementIterator-java.text.CharacterIterator-)