# JavaTuples 中的五重奏类

> 原文:[https://www.geeksforgeeks.org/quintet-class-in-java-tuples/](https://www.geeksforgeeks.org/quintet-class-in-java-tuples/)

一个**五重奏**是一个来自 **JavaTuples** 库的元组，处理 3 个元素。因为这个五重奏是一个类属，它可以包含任何类型的值。
由于五重奏是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```
public final class Quintet<A, B, C, D, E> extends Tuple
implements IValue0<A>, IValue1<B>, IValue2<C>, IValue3<D>, IValue4<E> 
```

### 类层次

```
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Quintet<A, B, C, D, E>
```

### 创建五元组

*   **从构造器**:
    T3】语法 :

```
Quintet<A, B, C, D, E> quintet = 
    new Quintet<A, B, C, D, E>
        (value1, value2, value3, value4, value5);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Quintet tuple from Constructor

import java.util.*;
import org.javatuples.Quintet;

class GfG {
    public static void main(String[] args)
    {
        Quintet<Integer, String, String, Double, Boolean> quintet
            = Quintet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18),
                           true);

        System.out.println(quintet);
    }
}
```

*   输出:

```
[1, GeeksforGeeks, A computer portal, 20.18, true]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **语法** :

```
Quintet<type1, type2, type3, type4, type5> quintet = 
    Quintet.with(value1, value2, value3, value4, value5);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Quintet tuple from with() method

import java.util.*;
import org.javatuples.Quintet;

class GfG {
    public static void main(String[] args)
    {
        Quintet<Integer, String, String, Double, Boolean> quintet
            = Quintet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18),
                           true);

        System.out.println(quintet);
    }
}
```

*   输出:

```
[1, GeeksforGeeks, A computer portal, 20.18, true]

```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **语法** :

```
Quintet<type1, type2, type3, type4, type5> quintet = 
    Quintet.fromCollection(collectionWith_5_value);

Quintet<type1, type2, type3, type4, type5> quintet = 
    Quintet.fromArray(arrayWith_5_value);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Quintet tuple from Collection

import java.util.*;
import org.javatuples.Quintet;

class GfG {
    public static void main(String[] args)
    {
        // Creating Quintet from List
        List<Integer> list = new ArrayList<Integer>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

        Quintet<Integer, Integer, Integer, Integer, Integer> quintet
            = Quintet.fromCollection(list);

        // Creating Quintet from Array
        Integer[] arr = { 1, 2, 3, 4, 5 };

        Quintet<Integer, Integer, Integer, Integer, Integer> otherQuintet
            = Quintet.fromArray(arr);

        System.out.println(quintet);
        System.out.println(otherQuintet);
    }
}
```

*   输出:

```
[1, 2, 3, 4, 5]
[1, 2, 3, 4, 5]
```

**获取值**
GetValueX()方法可用于获取索引 x 处元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。
**语法** :

```
Quintet<type1, type2, type3, type4, type5> quintet = 
    new Quintet<type1, type2, type3, type4, type5>
                   (value1, value2, value3, value4, value5);

type1 val1 = quintet.getValue0();
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to get
// a Quintet value

import java.util.*;
import org.javatuples.Quintet;

class GfG {
    public static void main(String[] args)
    {
        Quintet<Integer, String, String, Double, Boolean> quintet
            = Quintet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18),
                           true);

        System.out.println(quintet.getValue0());
        System.out.println(quintet.getValue2());
    }
}
```

输出:

```
1
A computer portal
```

**设置五重奏值**

由于元组是**不可变的**，这意味着修改索引处的值是不可能的。因此，JavaTuples 提供 **setAtX(value)** ，它在索引 X 处创建一个带有新值的元组副本，并返回该元组。
**语法** :

```
Quintet<type1, type2, type3, type4, type5> quintet = 
    new Quintet<type1, type2, type3, type4, type5>
                  (value1, value2, value3, value4, value5);

Quintet<type1, type2, type3, type4, type5> 
    otherQuintet = quintet.setAtX(value);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to set
// a Quintet value

import java.util.*;
import org.javatuples.Quintet;

class GfG {
    public static void main(String[] args)
    {
        Quintet<Integer, String, String, Double, Boolean> quintet
            = Quintet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18),
                           true);

        Quintet<Integer, String, String, Double> otherQuintet
            = quintet.setAt3(2.018);

        System.out.println(otherQuintet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal, 2.018, true]
```

**加值**
加值可以借助 addAtX()方法完成，其中 X 代表要加值的索引。这个方法返回一个比被调用的元组多一个元素的元组。
**语法** :

```
Quintet<type1, type2, type3, type4, type5> quintet = 
    new Quintet<type1, type2, type3, type4, type5>
                   (value1, value2, value3, value4, value5);

Quintet<type 1, type 2, type 3, type 4, type 5> quintet = 
    quintet.addAtx(value);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to add
// a value

import java.util.*;
import org.javatuples.Quintet;
import org.javatuples.Sextet;

class GfG {
    public static void main(String[] args)
    {
        Quintet<Integer, String, String, Double, Boolean> quintet
            = Quintet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18),
                           true);

        Quintet<Integer, String, String, Double, Boolean, Boolean> sextet
            = quintet.addAt5(false);

        System.out.println(sextet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal, for geeks, 20.18, true, false]
```

**在五重奏中搜索**

可以使用预定义的方法**在元组中搜索元素，该方法包含()**。无论该值是否存在，它都会返回一个布尔值。
**语法** :

```
Quintet<type1, type2, type3, type4, type5> quintet = 
    new Quintet<type1, type2, type3, type4, type5>
                   (value1, value2, value3, value4, value5);

boolean res = quintet.contains(value2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to search
// a value in a Quintet

import java.util.*;
import org.javatuples.Quintet;

class GfG {
    public static void main(String[] args)
    {
        Quintet<Integer, String, String, Double, Boolean> quintet
            = Quintet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18),
                           true);

        boolean exist = quintet.contains(20.18);
        boolean exist1 = quintet.contains(false);

        System.out.println(exist);
        System.out.println(exist1);
    }
}
```