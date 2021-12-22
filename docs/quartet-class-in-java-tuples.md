# JavaTuples 中的四重奏类

> 原文:[https://www.geeksforgeeks.org/quartet-class-in-java-tuples/](https://www.geeksforgeeks.org/quartet-class-in-java-tuples/)

一个**四元组**是一个来自 **JavaTuples** 库的元组，处理 4 个元素。因为这个四重奏是一个通用类，所以它可以包含任何类型的值。

由于四重奏是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```
public final class Quartet<A, B, C, D> extends Tuple
implements IValue0<A>, IValue1<B>, IValue2<C>, IValue3<D> 
```

### 类层次

```
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Quartet<A, B, C, D>
```

### 创建四元组

*   **从建造师**:
    T3】语法:

```
Quartet<A, B, C, D> quartet = 
    new Quartet<A, B, C, D>
        (value1, value2, value3, value4);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Quartet tuple from Constructor

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18));

        System.out.println(quartet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal, 20.18]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **句法**:

```
Quartet<type1, type2, type3, type4> quartet = 
    Quartet.with(value1, value2, value3, value4);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Quartet tuple from with() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18));

        System.out.println(quartet);
    }
}
```

输出:

```
[1, GeeksforGeeks, A computer portal, 20.18]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **句法**:

```
Quartet<type1, type2, type3, type4> quartet = 
    Quartet.fromCollection(collectionWith_2_value);

Quartet<type1, type2, type3, type4> quartet = 
    Quartet.fromArray(arrayWith_2_value);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Quartet tuple from Collection

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Creating Quartet from List
        List<String> list = new ArrayList<String>();
        list.add("GeeksforGeeks");
        list.add("A computer portal");
        list.add("for geeks");
        list.add("by Sandeep Jain");

        Quartet<Strin, String, String, String> quartet
            = Quartet.fromCollection(list);

        // Creating Quartet from Array
        String[] arr = { "GeeksforGeeks",
                         "A computer portal",
                         "for geeks",
                         "by Sandeep Jain" };

        Quartet<String, String, String, String> otherQuartet
            = Quartet.fromArray(arr);

        System.out.println(quartet);
        System.out.println(otherQuartet);
    }
}
```

输出:

```
[GeeksforGeeks, A computer portal, for geeks, by Sandeep Jain]
[GeeksforGeeks, A computer portal, for geeks, by Sandeep Jain]
```

### 获取价值

getValueX()方法可用于在索引 x 处获取元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。

**语法**:

```
Quartet<type1, type2, type3, type4> quartet = 
    new Quartet<type1, type2, type3, type4>(value1, value2, value3, value4);

type1 val1 = quartet.getValue0();
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to get
// a Quartet value

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18));

        System.out.println(quartet.getValue0());
        System.out.println(quartet.getValue2());
    }
}
```