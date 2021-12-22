# 在 Java 中打印将自定义类对象作为键或值的树形图

> 原文:[https://www . geesforgeks . org/printing-tree map-having-custom-class-objects-as-key-or-values-in-Java/](https://www.geeksforgeeks.org/printing-treemap-having-custom-class-objects-as-keys-or-values-in-java/)

[TreeMap](https://www.geeksforgeeks.org/treemap-in-java/) 是一个根据其键的自然顺序保持其条目排序的地图实现。因此，对于整数，这意味着升序，对于字符串，这将是字母顺序。TreeMap 也可以在构建时通过使用比较器根据用户进行排序。

在这里，我们将看到如何打印具有自定义类对象作为键或值的树形图。但在此之前，让我们看看正常打印时会发生什么。尝试打印对象时，直接打印的值可能格式不正确，在许多情况下，垃圾值(如@agc1243)会打印在输出端。

正常打印实现:

## Java

T0T6T8】输出 T10】

```java
1=>Student@3941a79c
2=>Student@506e1b77
3=>Student@4fca772d
```