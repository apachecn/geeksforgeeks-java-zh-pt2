# JavaTuples 中的八位字节类

> 原文:[https://www.geeksforgeeks.org/octet-class-in-java-tuples/](https://www.geeksforgeeks.org/octet-class-in-java-tuples/)

一个**八位字节**是一个来自 **JavaTuples** 库的元组，处理 3 个元素。因为这个八位字节是一个泛型类，所以它可以包含任何类型的值。
由于八位字节是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

**班级申报**

```java
public final class Octet<A, B, C, D, E, F, G, H> extends Tuple
implements IValue0<A>, IValue1<B>, IValue2<C>, IValue3<D>, IValue4<E>, 
                                            IValue5<F, IValue6<G, IValue7<H>
```

**等级等级**

```java
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Octet<A, B, C, D, E, F, G, H>
```

**创建八位字节元组**

**从构造器**:
T3】语法 :

```java
Octet<A, B, C, D, E, F, G, H> octet = 
    new Octet<A, B, C, D, E, F, G, H>
        (value1, value2, value3, value4, value5, value6, value7, value8);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Octet tuple from Constructor

import java.util.*;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = Octet.with(Integer.valueOf(1),
                         Integer.valueOf(2),
                         Integer.valueOf(3),
                         Integer.valueOf(4),
                         Integer.valueOf(5),
                         Integer.valueOf(6),
                         Integer.valueOf(7),
                         Integer.valueOf(8));

        System.out.println(octet);
    }
}
```

*   输出:

```java
[1, 2, 3, 4, 5, 6, 7, 8]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **语法** :

```java
Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    Octet.with(value1, value2, value3, value4, value5, value6, value7, value8);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Octet tuple from with() method

import java.util.*;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = Octet.with(Integer.valueOf(1),
                         Integer.valueOf(2),
                         Integer.valueOf(3),
                         Integer.valueOf(4),
                         Integer.valueOf(5),
                         Integer.valueOf(6),
                         Integer.valueOf(7),
                         Integer.valueOf(8));

        System.out.println(octet);
    }
}
```

*   输出:

```java
[1, 2, 3, 4, 5, 6, 7, 8]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **语法** :

```java
Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    Octet.fromCollection(collectionWith_8_value);

Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    Octet.fromArray(arrayWith_8_value);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Octet tuple from Collection

import java.util.*;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        // Creating Octet from List
        List<Integer> list = new ArrayList<Integer>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(8);

        Octet<Integer, Integer, Integer, Integer, Integer, Integer, Integer> octet
            = Octet.fromCollection(list);

        // Creating Octet from Array
        Integer[] arr = { 1, 2, 3, 4, 5, 6, 7, 8 };

        Octet<Integer, Integer, Integer, Integer, Integer, Integer, Integer> otherOctet
            = Octet.fromArray(arr);

        System.out.println(octet);
        System.out.println(otherOctet);
    }
}
```

*   输出:

```java
[1, 2, 3, 4, 5, 6, 7, 8]
[1, 2, 3, 4, 5, 6, 7, 8]
```

**获取值**
GetValueX()方法可用于获取索引 x 处元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。
**语法** :

```java
Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    new Octet<type1, type2, type3, type4, type5, type6, type7>
        (value1, value2, value3, value4, value5, value6, value7, value8);

type1 val1 = octet.getValue0();
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to get
// a Octet value

import java.util.*;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = Octet.with(Integer.valueOf(1),
                         Integer.valueOf(2),
                         Integer.valueOf(3),
                         Integer.valueOf(4),
                         Integer.valueOf(5),
                         Integer.valueOf(6),
                         Integer.valueOf(7),
                         Integer.valueOf(8));

        System.out.println(octet.getValue0());
        System.out.println(octet.getValue2());
    }
}
```

输出:

```java
1
3
```

### 设置八位字节值

由于元组是**不可变的**，这意味着修改索引处的值是不可能的。因此，JavaTuples 提供 **setAtX(value)** ，它在索引 X 处创建一个带有新值的元组副本，并返回该元组。
**语法** :

```java
Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    new Octet<type1, type2, type3, type4, type5, type6, type7>
      (value1, value2, value3, value4, value5, value6, value7, value8);

Octet<type1, type2, type3, type4, type5, type6, type7> 
    otherOctet = octet.setAtX(value);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to set
// a Octet value

import java.util.*;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = Octet.with(Integer.valueOf(1),
                         Integer.valueOf(2),
                         Integer.valueOf(3),
                         Integer.valueOf(4),
                         Integer.valueOf(5),
                         Integer.valueOf(6),
                         Integer.valueOf(7),
                         Integer.valueOf(8));

        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> otherOctet
            = octet.setAt3(40);

        System.out.println(otherOctet);
    }
}
```

输出:

```java
[1, 2, 3, 40, 5, 6, 7, 8]
```

**添加一个值**

添加一个值可以借助 **addAtX()** 方法完成，其中 X 代表要添加该值的索引。这个方法返回一个比被调用的元组多一个元素的元组。
**语法** :

```java
Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    new Octet<type1, type2, type3, type4, type5, type6, type7>
        (value1, value2, value3, value4, value5, value6, value7, value8);

Octet<type 1, type 2, type 3, type 4, type 5, type 6, type 7> octet = 
    octet.addAtx(value);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to add
// a value

import java.util.*;
import org.javatuples.Octet;
import org.javatuples.Ennead;

class GfG {
    public static void main(String[] args)
    {
        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = Octet.with(Integer.valueOf(1),
                         Integer.valueOf(2),
                         Integer.valueOf(3),
                         Integer.valueOf(4),
                         Integer.valueOf(5),
                         Integer.valueOf(6),
                         Integer.valueOf(7),
                         Integer.valueOf(8));

        Ennead<Integer, Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> ennead
            = octet.addAt8(9);

        System.out.println(ennead);
    }
}
```

输出:

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### 八位字节搜索

可以使用预定义的方法**在元组中搜索元素，该方法包含()**。无论该值是否存在，它都会返回一个布尔值。
**语法** :

```java
Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    new Octet<type1, type2, type3, type4, type5, type6, type7>
        (value1, value2, value3, value4, value5, value6, value7, value8);

boolean res = octet.contains(value2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to search
// a value in a Octet

import java.util.*;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = Octet.with(Integer.valueOf(1),
                         Integer.valueOf(2),
                         Integer.valueOf(3),
                         Integer.valueOf(4),
                         Integer.valueOf(5),
                         Integer.valueOf(6),
                         Integer.valueOf(7),
                         Integer.valueOf(8));

        boolean exist = octet.contains(5);
        boolean exist1 = octet.contains(false);

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

**遍历八位字节**

因为八位字节实现了**可迭代<对象>T1】接口。这意味着它们可以像集合或数组一样迭代。
**语法** :** 

```java
Octet<type1, type2, type3, type4, type5, type6, type7> octet = 
    new Octet<type1, type2, type3, type4, type5, type6, type7>
            (value1, value2, value3, value4, value5, value6, value7, value8);

for (Object item : octet) {
        ...
}
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to iterate
// a Octet

import java.util.*;
import org.javatuples.Octet;

class GfG {
    public static void main(String[] args)
    {
        Octet<Integer, Integer, Integer.Integer, Integer, Integer, Integer, Integer> octet
            = Octet.with(Integer.valueOf(1),
                         Integer.valueOf(2),
                         Integer.valueOf(3),
                         Integer.valueOf(4),
                         Integer.valueOf(5),
                         Integer.valueOf(6),
                         Integer.valueOf(7),
                         Integer.valueOf(8));

        for (Object item : octet)
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
8
```