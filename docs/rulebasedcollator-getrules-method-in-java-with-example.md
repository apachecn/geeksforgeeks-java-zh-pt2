# Java 中的 RuleBasedCollator getRules()方法，示例

> 原文:[https://www . geesforgeks . org/rulesbasedcollator-getrules-method-in-Java-with-example/](https://www.geeksforgeeks.org/rulebasedcollator-getrules-method-in-java-with-example/)

**Java . text . rulesbasedcollator 类**的 **getRules()** 方法用于获取基于规则的排序器对象初始化时使用的规则。

**语法:**

```
public String getRules()
```

**参数**:该方法不接受任何参数作为参数。
**返回值:**该方法返回基于规则的排序器对象初始化时使用的规则。

以下是说明 **getRules()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getRules() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a < c & a < b";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting rule of this object
            // using getRules() method
            String rule = col.getRules();

            // display result
            System.out.println("rule is :- "
                               + rule);
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

**Output:** 

```
rule is :- < a < c & a < b
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getRules() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing new simple rule
            String simple = "< a < b < c < d";

            // Creating and initializing
            // new RuleBasedCollator Object
            RuleBasedCollator col
                = new RuleBasedCollator(simple);

            // getting rule of this object
            // using getRules() method
            String rule = col.getRules();

            // display result
            System.out.println("rule is :- "
                               + rule);
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

**Output:** 

```
rule is :- < a < b < c < d
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/rulesbasedcollator . html # getRules–T4】