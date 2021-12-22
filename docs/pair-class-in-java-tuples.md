# JavaTuples 中的配对类

> 原文:[https://www.geeksforgeeks.org/pair-class-in-java-tuples/](https://www.geeksforgeeks.org/pair-class-in-java-tuples/)

一个**对**是一个来自 [**JavaTuples**](https://www.geeksforgeeks.org/javatuples-introduction/) 库的元组，处理 2 个元素。因为这个 Pair 是一个泛型类，所以它可以保存任何类型的值。
由于 Pair 是一个 Tuple，因此它也具有 JavaTuples 的所有特性:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```java
public final class Pair<A, B> extends Tuple 
           implements IValue0<A>, IValue1<B> 
```

### 类层次

```java
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Pair<A, B> 
```

### 创建对元组

*   **从建造师**:
    T3】语法:

```java
Pair<A, B> pair = new Pair<A, B>(value1, value2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Pair tuple from Constructor

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        Pair<Integer, String> pair
            = new Pair<Integer, String>(Integer.valueOf(1), "GeeksforGeeks");

        System.out.println(pair);
    }
}
```

输出:

```java
[1, GeeksforGeeks]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **句法**:

```java
Pair<type1, type2> pair = Pair.with(value1, value2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Pair tuple from with() method

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        Pair<Integer, String> pair
            = Pair.with(Integer.valueOf(1), "GeeksforGeeks");

        System.out.println(pair);
    }
}
```

输出:

```java
[1, GeeksforGeeks]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **句法**:

```java
Pair<type1, type2> pair = Pair.fromCollection(collectionWith_2_value);
Pair<type1, type2> pair = Pair.fromArray(arrayWith_2_value);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Pair tuple from Collection

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        // Creating Pair from List
        List<String> list = new ArrayList<String>();
        list.add("GeeksforGeeks");
        list.add("A computer portal");
        Pair<Strin, String> pair
            = Pair.fromCollection(list);

        // Creating Pair from Array
        String[] arr = { "GeeksforGeeks", "A computer portal" };
        Pair<String, String> otherPair
            = Pair.fromArray(arr);

        System.out.println(pair);
        System.out.println(otherPair);
    }
}
```

输出:

```java
[GeeksforGeeks, A computer portal]
[GeeksforGeeks, A computer portal] 
```

### 获取价值

getValueX()方法可用于在索引 x 处获取元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。

**语法**:

```java
Pair<type1, type2> pair = 
    new Pair<type1, type2>(value1, value2);

type1 val1 = pair.getValue0();
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to get
// a Pair value

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        Pair<Integer, String> pair
            = Pair.with(Integer.valueOf(1), "GeeksforGeeks");

        System.out.println(pair.getValue0());
    }
}
```

输出:

```java
1 
```

### 设置对值

由于元组是不可变的，这意味着修改索引处的值是不可能的。因此，JavaTuples 提供了 setAtX(value)，它用索引 X 处的新值创建元组的副本，并返回该元组。

**语法**:

```java
Pair<type1, type2> pair = 
    new Pair<type1, type2>(value1, value2);

type1 val1 = pair.getValue0();
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to set
// a Pair value

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        Pair<Integer, String> pair
            = Pair.with(Integer.valueOf(1), "GeeksforGeeks");

        Pair<Integer, String> otherPair
            = pair.setAt1("A computer portal");

        System.out.println(otherPair);
    }
}
```

输出:

```java
[1, A computer portal] 
```

### 添加值

添加一个值可以在 addAtX()方法的帮助下完成，其中 X 表示要添加该值的索引。这个方法返回一个比被调用的元组多一个元素的元组。

**语法**:

```java
Pair<type1, type2> pair = 
    new Pair<type1, type2>(value1, value2);

Triplet<type 1, type 2, type 3> pair = 
    pair.addAt2(value 2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to add
// a value

import java.util.*;
import org.javatuples.Pair;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        Pair<Integer, String> pair
            = Pair.with(Integer.valueOf(1), "GeeksforGeeks");

        Triplet<Integer, String, String> triplet
            = pair.addAt2("A computer portal");

        System.out.println(triplet);
    }
}
```

输出:

```java
[1, GeeksforGeeks, A computer portal] 
```

### 成对搜索

可以使用预定义的方法**在元组中搜索元素，该方法包含()**。无论该值是否存在，它都会返回一个布尔值。

**语法**:

```java
Pair<type1, type2> pair = 
    new Pair<type1, type2>(value1, value2);

boolean res = pair.contains(value2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to search
// a value

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        Pair<Integer, String> pair
            = Pair.with(Integer.valueOf(1), "GeeksforGeeks");

        boolean exist = pair.contains("GeeksforGeeks");
        boolean exist1 = pair.contains(4);

        System.out.println(exist);
        System.out.println(exist1);
    }
}
```

输出:

```java
true
false 
```

### 遍历对

因为 Pair 实现了**可迭代<对象>T1】接口。这意味着它们可以像集合或数组一样迭代。**

**语法**:

```java
Pair<type1, type2> pair = 
    new Pair<type1, type2>(value1, value2);

for (Object item : pair) {
        ...
}
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to iterate
// a Pair

import java.util.*;
import org.javatuples.Pair;

class GfG {
    public static void main(String[] args)
    {
        Pair<Integer, String> pair
            = Pair.with(Integer.valueOf(1), "GeeksforGeeks");

        for (Object item : pair)
            System.out.println(item);
    }
}
```

输出:

```java
1
GeeksforGeeks
```