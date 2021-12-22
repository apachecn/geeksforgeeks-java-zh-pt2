# 拆分器限制()方法|番石榴| Java

> 原文:[https://www . geesforgeks . org/splitter-limit-method-guava-Java/](https://www.geeksforgeeks.org/splitter-limit-method-guava-java/)

方法 **limit(int limit)** 返回一个行为与此拆分器等效的拆分器，但在达到限制后停止拆分。该限制定义了 ***迭代器*** 返回的最大项目数，或者***splitToList(Java . lang . charsequence)***返回的列表的最大大小。
例如， **Splitter.on('，')。极限(3)。拆分(“a，b，c，d”)**返回一个包含**[“a”，“b”，“c，d”]的可迭代表。**

**语法:**

```
public Splitter limit(int limit)

```

**参数:**该方法以*极限*为参数，该参数为返回的最大项数。

**返回值:**该方法返回具有所需配置的拆分器。

**例 1:**

```
// Java code to show implementation of
// limit(int limit) method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a string variable
        String str = "geeks, .  for, .Hey.,  "
                     + "geeks, ., noida, ., classes";

        // Initially setting limit as 3
        System.out.println("When Limit is 3 : ");

        // Using limit(int limit) method which
        // stops splitting after it reaches the limit.
        Iterable<String> result = Splitter.on(',')
                                      .limit(3)
                                      .trimResults()
                                      .split(str);
        for (String temp : result) {
            System.out.println(temp);
        }

        // Setting limit as 4
        System.out.println("\n\nWhen Limit is 4 : ");

        // Using limit(int limit) method which
        // stops splitting after it reaches the limit.
        Iterable<String> result1 = Splitter.on(',')
                                       .limit(4)
                                       .trimResults()
                                       .split(str);
        for (String temp : result1) {
            System.out.println(temp);
        }
    }
}
```

**Output:**

```
When Limit is 3 : 
geeks
.  for
.Hey.,  geeks, ., noida, ., classes

When Limit is 4 : 
geeks
.  for
.Hey.
geeks, ., noida, ., classes

```

**例 2:**

```
// Java code to show implementation of
// limit(int limit) method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a string variable
        String str = "Learn$,,Data $ structures"
                     + " 123$ to be $ best Coder..";

        // Initially setting limit as 2
        System.out.println("When Limit is 2 : ");

        // Using limit(int limit) method which
        // stops splitting after it reaches the limit.
        Iterable<String> result = Splitter.on('{content}apos;)
                                      .limit(2)
                                      .trimResults()
                                      .split(str);
        for (String temp : result) {
            System.out.println(temp);
        }

        // Setting limit as 4
        System.out.println("\n\nWhen Limit is 4 : ");

        // Using limit(int limit) method which
        // stops splitting after it reaches the limit.
        Iterable<String> result1 = Splitter.on('{content}apos;)
                                       .limit(4)
                                       .trimResults()
                                       .split(str);
        for (String temp : result1) {
            System.out.println(temp);
        }
    }
}
```

**Output:**

```
When Limit is 2 : 
Learn,,Data $ structures 123$ to be $ best Coder..

When Limit is 4 : 
Learn,,Data
structures 123
to be $ best Coder..

```

**注:**

*   省略空字符串时，省略的字符串不计算在内。因此，Splitter.on('，')。极限(3)。omitEmptyStrings()。split("a、、b、、、、c、d ")返回一个包含["a "、" b "、" c、d"]的 iterable。
*   请求修剪时，所有条目都会被修剪，包括最后一个条目。因此 Splitter.on('，')。极限(3)。trimResults()。拆分(“a、b、c、d”)导致[“a”、“b”、“c、d”]。