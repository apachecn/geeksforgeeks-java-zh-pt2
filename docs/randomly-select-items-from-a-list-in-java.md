# 从 Java 列表中随机选择项目

> 原文:[https://www . geesforgeks . org/从 java 列表中随机选择项目/](https://www.geeksforgeeks.org/randomly-select-items-from-a-list-in-java/)

在本文中，我们将展示最有效的方法，从列表中查找或挑选一个元素。从列表中选择项目的基本思想是，首先生成一个介于 0 和列表大小之间的数字。

**1。单个随机项目**

首先，我们为使用 Random.nextInt(int bound)方法选择一个随机索引。代替 Random 类，您可以始终使用静态方法 Math.random()(random()方法生成一个 0 到 1 之间的数字)并将其与列表大小相乘。

## 爪哇

T0】输出

```
30
```