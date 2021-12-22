# Splitter trimResults()方法|番石榴|爪哇

> 原文:[https://www . geesforgeks . org/splitter-trimresults-method-guava-Java/](https://www.geeksforgeeks.org/splitter-trimresults-method-guava-java/)

方法 **trimResults()** 返回一个行为与此拆分器相同的拆分器，但会自动从每个返回的子字符串中移除前导的*和尾随的*空格。例如，
**Splitter.on('，')。trimResults()。split(" a，b，c ")** 返回一个包含 **["a "、" b "、" c"]** 的可迭代表。**

****语法:****

```
**public Splitter trimResults()** 
```

****返回值:**该方法返回具有所需配置的拆分器。**

****例 1:****

```
**// Java code to show implementation of
// trimResults() method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a string variable
        String str = "Hello,  geeks, for,  geeks,  noida";

        // Using trimResults() method. Strings that
        // have been split apart often need to be
        // trimmed. They often have surrounding whitespace.
        // With trimResults(), Splitter does this.
        List<String> myList = Splitter.on(',')
          .trimResults().splitToList(str);

        for (String temp : myList) {
            System.out.println(temp);
        }
    }
}**
```

****Output:**

```
Hello
geeks
for
geeks
noida

```** 

****例 2:****

```
**// Java code to show implementation of
// trimResults() method
// of Guava's Splitter Class

import com.google.common.base.Splitter;
import java.util.List;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a string variable
        String str = "Everyone. .  should. Learn. Data. Structures";

        // Using trimResults() method. Strings that
        // have been split apart often need to be
        // trimmed. They often have surrounding whitespace.
        // With trimResults(), Splitter does this.
        List<String> myList = Splitter.on('.')
            .trimResults().splitToList(str);

        for (String temp : myList) {
            System.out.println(temp);
        }
    }
}**
```

****Output:**

```
Everyone

should
Learn
Data
Structures

```**