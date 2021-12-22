# 在 Java 中打乱或随机化列表

> 原文:[https://www . geesforgeks . org/shuffle-or-随机化-a-list-in-java/](https://www.geeksforgeeks.org/shuffle-or-randomize-a-list-in-java/)

*   **洗牌列表**
    [collections . shuffle()](https://www.geeksforgeeks.org/collections-shuffle-java-examples/)是 java 中用来洗牌的列表。
    等级体系:

```java
java
   ↳ util
      ↳ Collections
```

语法:

```java
Collections.shuffle(list);
```

示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of shuffle()
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        ArrayList<String> mylist = new ArrayList<String>();
        mylist.add("ide");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");
        mylist.add("quiz");
        mylist.add("practice");
        mylist.add("qa");

        System.out.println("Original List : \n" + mylist);

        Collections.shuffle(mylist);

        System.out.println("\nShuffled List : \n" + mylist);
    }
}
```

**Output:** 

```java
Original List : 
[ide, quiz, geeksforgeeks, quiz, practice, qa]

Shuffled List : 
[ide, practice, quiz, qa, geeksforgeeks, quiz]
```