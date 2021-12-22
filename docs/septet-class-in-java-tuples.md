# JavaTuples 中的九月类

> 原文:[https://www.geeksforgeeks.org/septet-class-in-java-tuples/](https://www.geeksforgeeks.org/septet-class-in-java-tuples/)

一个**九元组**是一个来自 **JavaTuples** 库的元组，处理 3 个元素。因为这个 Septet 是一个泛型类，所以它可以保存任何类型的值。
由于 Septet 是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```java
public final class Septet<A, B, C, D, E, F, G> extends Tuple
implements IValue0<A>, IValue1<B>, IValue2<C>, IValue3<D>, IValue4<E>, IValue5<F, IValue6<G>
```

### 类层次

```java
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Septet<A, B, C, D, E, F, G>
```

### 创建七元组

*   **从构造器**:
    T3】语法 :

```java
Septet<A, B, C, D, E, F, G> septet = 
    new Septet<A, B, C, D, E, F, G>
        (value1, value2, value3, value4, value5, value6, value7);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Septet tuple from Constructor

import java.util.*;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> septet
            = Septet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7));

        System.out.println(septet);
    }
}
```

*   输出:

```java
[1, 2, 3, 4, 5, 6, 7]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **语法** :

```java
Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    Septet.with(value1, value2, value3, value4, value5, value6, value7);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Septet tuple from with() method

import java.util.*;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> septet
            = Septet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7));

        System.out.println(septet);
    }
}
```

*   输出:

```java
[1, 2, 3, 4, 5, 6, 7]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **语法** :

```java
Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    Septet.fromCollection(collectionWith_7_value);

Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    Septet.fromArray(arrayWith_7_value);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Septet tuple from Collection

import java.util.*;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        // Creating Septet from List
        List<Integer> list = new ArrayList<Integer>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);
        list.add(6);
        list.add(7);

        Septet<Integer, Integer, Integer, Integer, Integer, Integer> septet
            = Septet.fromCollection(list);

        // Creating Septet from Array
        Integer[] arr = { 1, 2, 3, 4, 5, 6, 7 };

        Septet<Integer, Integer, Integer, Integer, Integer, Integer> otherSeptet
            = Septet.fromArray(arr);

        System.out.println(septet);
        System.out.println(otherSeptet);
    }
}
```

*   输出:

```java
[1, 2, 3, 4, 5, 6, 7]
[1, 2, 3, 4, 5, 6, 7]
```

### 获取价值

getValueX()方法可用于在索引 x 处获取元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。
**语法** :

```java
Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    new Septet<type1, type2, type3, type4, type5, type6, type7>
        (value1, value2, value3, value4, value5, value6, value7);

type1 val1 = septet.getValue0();
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to get
// a Septet value

import java.util.*;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> septet
            = Septet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7));

        System.out.println(septet.getValue0());
        System.out.println(septet.getValue2());
    }
}
```

输出:

```java
1
3
```

### 设置七分之一值

由于元组是**不可变的**，这意味着在任何索引处修改值都是不可能的。因此，JavaTuples 提供 **setAtX(value)** ，它在索引 X 处创建一个带有新值的元组副本，并返回该元组。
**语法** :

```java
Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    new Septet<type1, type2, type3, type4, type5, type6, type7>
                (value1, value2, value3, value4, value5, value6, value7);

Septet<type1, type2, type3, type4, type5, type6, type7> 
    otherSeptet = septet.setAtX(value);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to set
// a Septet value

import java.util.*;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> septet
            = Septet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7));

        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> otherSeptet
            = septet.setAt3(40);

        System.out.println(otherSeptet);
    }
}
```

输出:

```java
[1, 2, 3, 40, 5, 6, 7]
```

### 添加值

添加一个值可以借助 **addAtX()** 方法完成，其中 X 代表要添加该值的索引。这个方法返回一个比被调用的元组多一个元素的元组。
**语法** :

```java
Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    new Septet<type1, type2, type3, type4, type5, type6, type7>
        (value1, value2, value3, value4, value5, value6, value7);

Septet<type 1, type 2, type 3, type 4, type 5, type 6, type 7> septet = 
    septet.addAtx(value);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to add
// a value

import java.util.*;
import org.javatuples.Septet;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> septet
            = Septet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7));

        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = septet.addAt7(8);

        System.out.println(octet);
    }
}
```

输出:

```java
[1, 2, 3, 4, 5, 6, 7, 8]
```

### 在九月寻找

可以使用预定义的方法**在元组中搜索元素，该方法包含()**。无论该值是否存在，它都会返回一个布尔值。
**语法** :

```java
Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    new Septet<type1, type2, type3, type4, type5, type6, type7>
        (value1, value2, value3, value4, value5, value6, value7);

boolean res = septet.contains(value2);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to search
// a value in a Septet

import java.util.*;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> septet
            = Septet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7));

        boolean exist = septet.contains(5);
        boolean exist1 = septet.contains(false);

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

### 迭代塞普特

自九月起实现**可迭代<对象>T1 界面。这意味着它们可以像集合或数组一样迭代。
**语法** :** 

```java
Septet<type1, type2, type3, type4, type5, type6, type7> septet = 
    new Septet<type1, type2, type3, type4, type5, type6, type7>
            (value1, value2, value3, value4, value5, value6, value7);

for (Object item : septet) {
        ...
}
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to iterate
// a Septet

import java.util.*;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        Septet<Integer, Integer.Integer, Integer, Integer, Integer, Integer> septet
            = Septet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7));

        for (Object item : septet)
            System.out.println(item);
    }
}
```

输出:

```java
1
2
3
4
5
6
7
```