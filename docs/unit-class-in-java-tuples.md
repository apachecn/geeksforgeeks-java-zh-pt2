# JavaTuples 中的单元类

> 原文:[https://www.geeksforgeeks.org/unit-class-in-java-tuples/](https://www.geeksforgeeks.org/unit-class-in-java-tuples/)

一个**单元**是一个来自 [**的元组**](https://www.geeksforgeeks.org/javatuples-introduction/) 库，只处理一个元素。因为这个单元是一个泛型类，所以它可以包含任何类型的值。
由于单位是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```
public final class Unit<A> extends Tuple implements IValue0<A> 
```

### 类层次

```
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Unit<A>
```

**创建单位元组**

*   **从构造器**:
    T3】语法 :

```
Unit<A> unit = new Unit<A>(value);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Unit tuple from Constructor

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        Unit<String> unit
            = new Unit<String>("GeeksforGeeks");

        System.out.println(unit);
    }
}
```

*   输出:

```
[GeeksforGeeks]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **语法** :

```
Unit<type 1> unit = Unit.with(value);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Unit tuple from with() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        Unit<String> unit
            = Unit.with("GeeksforGeeks");

        System.out.println(unit);
    }
}
```