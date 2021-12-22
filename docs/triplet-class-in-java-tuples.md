# JavaTuples 中的三元组类

> 原文:[https://www.geeksforgeeks.org/triplet-class-in-java-tuples/](https://www.geeksforgeeks.org/triplet-class-in-java-tuples/)

一个**三元组**是一个来自 **JavaTuples** 库的元组，处理 3 个元素。因为这个三元组是一个泛型类，所以它可以保存任何类型的值。

由于三元组是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```
public final class Triplet<A, B, C> extends Tuple
    implements IValue0<A>, IValue1<B>, IValue2<C> 
```

### 类层次

```
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Triplet<A, B, C> 
```

### 创建三元组元组

*   **从建造师**:
    T3】语法:

```
Triplet<A, B, C> triplet = 
    new Triplet<A, B, C>(value1, value2, value3);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Triplet tuple from Constructor

import java.util.*;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        Triplet<Integer, String, String> triplet
            = new Triplet<Integer, String, String>(Integer.valueOf(1),
                                "GeeksforGeeks", "A computer portal");

        System.out.println(triplet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **句法**:

```
Triplet<type1, type2, type3> triplet = 
       Triplet.with(value1, value2, value3);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Triplet tuple from with() method

import java.util.*;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        Triplet<Integer, String, String> triplet
            = Triplet.with(Integer.valueOf(1),
                           "GeeksforGeeks", "A computer portal");

        System.out.println(triplet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **句法**:

```
Triplet<type1, type2, type3> triplet = 
    Triplet.fromCollection(collectionWith_2_value);

Triplet<type1, type2, type3> triplet = 
    Triplet.fromArray(arrayWith_2_value);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Triplet tuple from Collection

import java.util.*;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        // Creating Triplet from List
        List<String> list = new ArrayList<String>();
        list.add("GeeksforGeeks");
        list.add("A computer portal");
        list.add("for geeks");

        Triplet<Strin, String, String> triplet
            = Triplet.fromCollection(list);

        // Creating Triplet from Array
        String[] arr = { "GeeksforGeeks",
                         "A computer portal",
                         "for geeks" };

        Triplet<String, String, String> otherTriplet
            = Triplet.fromArray(arr);

        System.out.println(triplet);
        System.out.println(otherTriplet);
    }
}
```

输出:

```
[GeeksforGeeks, A computer portal, for geeks]
[GeeksforGeeks, A computer portal, for geeks]
```

### 获取价值

getValueX()方法可用于在索引 x 处获取元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。

**语法**:

```
Triplet<type1, type2, type3> triplet = 
    new Triplet<type1, type2, type3>(value1, value2, value3);

type1 val1 = triplet.getValue0();
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to get
// a Triplet value

import java.util.*;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        Triplet<Integer, String, String> triplet
            = Triplet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal");

        System.out.println(triplet.getValue0());
        System.out.println(triplet.getValue2());
    }
}
```

输出:

```
1
A computer portal
```

### 设置三元组值

由于元组是**不可变的**，这意味着修改索引处的值是不可能的。因此，JavaTuples 提供了 **setAtX(value)** ，它在索引 X 处创建一个带有新值的元组副本，并返回该元组。

**语法**:

```
Triplet<type1, type2, type3> triplet = 
    new Triplet<type1, type2, type3>
                (value1, value2, value3);

Triplet<type1, type2, type3> 
    otherTriplet = triplet.setAtX(value);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to set
// a Triplet value

import java.util.*;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        Triplet<Integer, String, String> triplet
            = Triplet.with(Integer.valueOf(1), "GeeksforGeeks",
                                          "A computer portal");

        Triplet<Integer, String, String> otherTriplet
            = triplet.setAt1("A computer portal for geeks");

        System.out.println(otherTriplet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal for geeks]
```

### 添加值

添加一个值可以借助 **addAtX()** 方法完成，其中 X 代表要添加该值的索引。这个方法返回一个比被调用的元组多一个元素的元组。

**语法**:

```
Triplet<type1, type2, type3> triplet = 
    new Triplet<type1, type2, type3>(value1, value2, value3);

Quartet<type 1, type 2, type 3, type 4> quartet = 
    triplet.addAt3(value);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to add
// a value

import java.util.*;
import org.javatuples.Triplet;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        Triplet<Integer, String, String> triplet
            = Triplet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal");

        Quartet<Integer, String, String, String> quartet
            = triplet.addAt3("for geeks");

        System.out.println(quartet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal, for geeks]
```

### 三重搜索

可以使用预定义的方法**在元组中搜索元素，该方法包含()**。无论该值是否存在，它都会返回一个布尔值。

**语法**:

```
Triplet<type1, type2, type3> triplet = 
    new Triplet<type1, type2, type3>(value1, value2, value3);

boolean res = triplet.contains(value2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to search
// a value in a Triplet

import java.util.*;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        Triplet<Integer, String, String> triplet
            = Triplet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal");

        boolean exist = triplet.contains("GeeksforGeeks");
        boolean exist1 = triplet.contains(4);

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

### 遍历三元组

因为三元组实现了**可迭代<对象>T1】接口。这意味着它们可以像集合或数组一样迭代。**

**语法**:

```
Triplet<type1, type2, type3> triplet = 
    new Triplet<type1, type2, type3>(value1, value2, value3);

for (Object item : triplet) {
        ...
}
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to iterate
// a Triplet

import java.util.*;
import org.javatuples.Triplet;

class GfG {
    public static void main(String[] args)
    {
        Triplet<Integer, String, String> triplet
            = Triplet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal");

        for (Object item : triplet)
            System.out.println(item);
    }
}
```

输出:

```
1
GeeksforGeeks
A computer portal
```