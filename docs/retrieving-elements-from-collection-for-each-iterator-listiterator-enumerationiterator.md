# 在 Java 中从集合中检索元素(对于每个元素，迭代器，列表迭代器&枚举迭代器)

> 原文:[https://www . geeksforgeeks . org/retrieving-elements-from-collection-for-for-forever-list iterator-enumeration iterator/](https://www.geeksforgeeks.org/retrieving-elements-from-collection-for-each-iterator-listiterator-enumerationiterator/)

先决条件:[Java 中的集合](https://www.geeksforgeeks.org/collections-in-java-2/)
以下是从集合对象中检索任何元素的 4 种方法:

**For-each**

[对于每个](https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/)循环意味着遍历集合中的项目。

```java
// Iterating over collection 'c' using **for-each** 
   for (Element e: c)
       System.out.println(e);
```

我们将每个 for 循环中使用的“:”理解为“in”。所以循环读作“对于元素中的每个元素”，这里元素是存储元素类型项的集合。

**注意:**在使用 lambda 表达式的 Java 8 中，我们可以简单地用

```java
elements.forEach (e -> System.out.println(e) );
```

**使用光标**

游标是一个接口，用于逐个从集合对象中检索数据。光标有 3 种类型，如下所示:

**迭代器接口** : [迭代器](http://geeksquiz.com/how-to-use-iterator-in-java/)是集合框架提供的一个接口，用于遍历集合以及对集合中的项目进行顺序访问。

```java

   // Iterating over collection 'c' using iterator
   for (Iterator i = c.iterator(); i.hasNext(); ) 
       System.out.println(i.next());
```

1.  它有 3 种方法:
    *   ***布尔 hasNext():*** 如果迭代器有更多的元素，这个方法返回 true。
    *   ***元素 next()*** :这个方法返回迭代器中的下一个元素。
    *   ***void remove()*** :这个方法从集合中移除迭代器返回的最后一个元素。
2.  **列表迭代器接口**:这是一个包含从集合对象中检索元素的方法的接口，包括**正向和反向**。这个迭代器用于基于列表的集合。
    它有以下重要方法:
    *   ***booleanhassnext()***:如果列表迭代器在向前遍历列表时元素较多，则返回 true。
    *   ***booleanhassprevious()***:如果列表迭代器在反向遍历列表时元素较多，则返回 true。
    *   ***元素 next()*** :返回列表中下一个元素。
    *   ***元素 previous()*** :返回列表中的前一个元素。
    *   ***void remove()*** :这将从列表中删除由 next()或 previous()方法返回的最后一个元素。
    *   ***int nextIndex()*** 返回元素的索引，该索引将由对 next()的后续调用返回。(如果列表迭代器位于列表末尾，则返回列表大小。)
    *   ***int previousIndex()***返回对 previous()的后续调用将返回的元素的索引。(如果列表迭代器在列表的开头，则返回-1。)
3.  **枚举迭代器接口**:接口对于逐个检索元素很有用。这个迭代器基于来自枚举的数据，并且有方法:
    *   ***booleanhasmorelements()***:这个方法测试枚举是否还有其他元素。
    *   ***元素 nextElement()*** :这将返回 Enumeration 中可用元素中的下一个可用元素

**相关文章:**
[Java 中的迭代器](https://www.geeksforgeeks.org/iterators-in-java/)
[迭代器 vs Java 中的 Foreach](https://www.geeksforgeeks.org/iterator-vs-foreach-in-java/)
本文由 **Nishant Sharma 供稿。**如果你喜欢 GeeksforGeeks，想投稿，也可以写一篇文章，把文章发到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息