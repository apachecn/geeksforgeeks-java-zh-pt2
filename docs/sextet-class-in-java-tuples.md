# JavaTuples 中的六重奏类

> 原文:[https://www.geeksforgeeks.org/sextet-class-in-java-tuples/](https://www.geeksforgeeks.org/sextet-class-in-java-tuples/)

一个**六元组**是一个来自 **JavaTuples** 库的元组，处理 3 个元素。因为这个 Sextet 是一个泛型类，所以它可以保存任何类型的值。
由于六重奏是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```
public final class Sextet<A, B, C, D, E, F> extends Tuple
implements IValue0<A>, IValue1<B>, IValue2<C>, IValue3<D>, IValue4<E>, IValue5<F>
```

### 类层次

```
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Sextet<A, B, C, D, E, F>
```

### 创建六元组

*   **从构造器**:
    T3】语法 :

```
Sextet<A, B, C, D, E, F> sextet = 
    new Sextet<A, B, C, D, E. F>
        (value1, value2, value3, value4, value5, value6);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Sextet tuple from Constructor

import java.util.*;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> sextet
            = Sextet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6));

        System.out.println(sextet);
    }
}
```

*   输出:

```
[1, 2, 3, 4, 5, 6]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **语法** :

```
Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    Sextet.with(value1, value2, value3, value4, value5, value6);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Sextet tuple from with() method

import java.util.*;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> sextet
            = Sextet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6));

        System.out.println(sextet);
    }
}
```

*   输出:

```
[1, 2, 3, 4, 5, 6]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **语法** :

```
Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    Sextet.fromCollection(collectionWith_6_value);

Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    Sextet.fromArray(arrayWith_6_value);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Sextet tuple from Collection

import java.util.*;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        // Creating Sextet from List
        List<Integer> list = new ArrayList<Integer>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);
        list.add(6);

        Sextet<Integer, Integer, Integer, Integer, Integer, Integer> sextet
            = Sextet.fromCollection(list);

        // Creating Sextet from Array
        Integer[] arr = { 1, 2, 3, 4, 5, 6 };

        Sextet<Integer, Integer, Integer, Integer, Integer, Integer> otherSextet
            = Sextet.fromArray(arr);

        System.out.println(sextet);
        System.out.println(otherSextet);
    }
}
```

*   输出:

```
[1, 2, 3, 4, 5, 6]
[1, 2, 3, 4, 5, 6]
```

### 获取价值

getValueX()方法可用于在索引 x 处获取元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。
**语法** :

```
Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    new Sextet<type1, type2, type3, type4, type5, type6>
               (value1, value2, value3, value4, value5, value6);

type1 val1 = sextet.getValue0();
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to get
// a Sextet value

import java.util.*;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> sextet
            = Sextet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6));

        System.out.println(sextet.getValue0());
        System.out.println(sextet.getValue2());
    }
}
```

输出:

```
1
3
```

### 设置六位数值

由于元组是不可变的，这意味着修改索引处的值是不可能的。因此，JavaTuples 提供 **setAtX(value)** ，它在索引 X 处创建一个具有新值的元组副本，并返回该元组。
**语法** :

```
Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    new Sextet<type1, type2, type3, type4, type5, type6>
                (value1, value2, value3, value4, value5, value6);

Sextet<type1, type2, type3, type4, type5, type6> 
    otherSextet = sextet.setAtX(value);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to set
// a Sextet value

import java.util.*;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> sextet
            = Sextet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6));

        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> otherSextet
            = sextet.setAt3(40);

        System.out.println(otherSextet);
    }
}
```

输出:

```
[1, 2, 3, 40, 5, 6]
```

### 添加值

添加一个值可以在 addAtX()方法的帮助下完成，其中 X 表示要添加该值的索引。这个方法返回一个比被调用的元组多一个元素的元组。
**语法** :

```
Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    new Sextet<type1, type2, type3, type4, type5, type6>
        (value1, value2, value3, value4, value5, value6);

Sextet<type 1, type 2, type 3, type 4, type 5, type 6> sextet = 
    sextet.addAtx(value);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to add
// a value

import java.util.*;
import org.javatuples.Sextet;
import org.javatuples.Septet;

class GfG {
    public static void main(String[] args)
    {
        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> sextet
            = Sextet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6));

        Septet<Integer, Integer.Integer, Integer, Integer, Integer> septet
            = sextet.addAt6(7);

        System.out.println(septet);
    }
}
```

输出:

```
[1, 2, 3, 4, 5, 6, 7]
```

### 在六重奏中搜索

可以使用预定义的方法**在元组中搜索元素，该方法包含()**。无论该值是否存在，它都会返回一个布尔值。
**语法** :

```
Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    new Sextet<type1, type2, type3, type4, type5, type6>
        (value1, value2, value3, value4, value5, value6);

boolean res = sextet.contains(value2);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to search
// a value in a Sextet

import java.util.*;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> sextet
            = Sextet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6));

        boolean exist = sextet.contains(5);
        boolean exist1 = sextet.contains(false);

        System.out.println(exist);
        System.out.println(exist1);
    }
}
```

输出:

```
true
false
```

### 迭代六重奏

因为六位一体实现了**可迭代<对象>T1】接口。这意味着它们可以像集合或数组一样迭代。
**语法** :** 

```
Sextet<type1, type2, type3, type4, type5, type6> sextet = 
    new Sextet<type1, type2, type3, type4, type5, type6>
            (value1, value2, value3, value4, value5, value6);

for (Object item : sextet) {
        ...
}
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to iterate
// a Sextet

import java.util.*;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        Sextet<Integer, Integer.Integer, Integer, Integer, Integer> sextet
            = Sextet.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6));

        for (Object item : sextet)
            System.out.println(item);
    }
}
```

输出:

```
1
2
3
4
5
6
```