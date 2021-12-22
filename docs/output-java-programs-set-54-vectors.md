# Java 程序输出|集合 54(向量)

> 原文:[https://www . geesforgeks . org/output-Java-programs-set-54-vectors/](https://www.geeksforgeeks.org/output-java-programs-set-54-vectors/)

**先决条件:**[Java 基础中的向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)

**1。以下程序的输出是什么**

```
import java.util.*;
class demo1 {
    public static void main(String[] args)
    {
        Vector v = new Vector(20);
        System.out.println(v.capacity());
        System.out.println(v.size());
    }
}
```

**输出:**

```
20
0

```

**解释:**
函数–int capacity()返回向量的容量，即它能容纳多少元素。
函数–int size()返回当前向量中的元素个数。由于没有添加元素，因此为 0。

**2。以下程序的输出是什么**

```
import java.util.*;
class demo2 {
    public static void main(String[] args)
    {
        Vector v = new Vector(20);
        v.addElement("Geeksforgeeks");
        v.insertElementAt("Java", 2);
        System.out.println(v.firstElement());
    }
}
```

**输出:**

```
It gives no output because of ArrayindexOutOfBound Exception

```

**解释:**
这是因为最初索引 0 处只有一个元素。接下来，它希望在索引 1 处添加一个值，但是我们在索引 2 处添加。因此会引发异常。

**3。以下程序的输出是什么**

```
import java.util.*;
class demo3 {
    public static void main(String[] args)
    {
        Vector v = new Vector(20);
        v.addElement("Geeksforgeeks");
        v.insertElementAt("Java", 0);
        System.out.println(v.firstElement());
    }
}
```

**输出:**

```
Java

```

**解释:**
Void add Element(E)–元素 E 被添加到向量中
void insertElementAt(Object E，int index)–在索引指定的位置将元素 E 添加到向量中。
对象 first element()–返回向量中的第一个元素。

“Java”成为第一个元素，“Geeksforgeeks”成为第二个元素。

**4。以下程序的输出是什么**

```
import java.util.*;
class demo4 {
    public static void main(String[] args)
    {
        Vector v = new Vector(20);
        v.addElement("Geeksforgeeks");
        System.out.println(v.elementAt(1));
    }
}
```

**输出:**

```
No output because of ArrayIndexOutOfBound Exception

```

**解释:**
函数 elementAt(int index)返回索引指定位置的元素。
这里同样是在索引 0 处添加元素，数组的大小只有 1。
所以调用 elementAt(1)会引发一个异常，因为 1 号索引还不存在。

**5。以下程序的输出是什么**

```
import java.util.*;
class demo5 {
    public static void main(String[] args)
    {
        Vector v = new Vector(40);
        v.addElement("Geeksforgeeks");
        v.addElement("Programming");
        v.addElement("Java");
        System.out.println(v.firstElement());
        System.out.println(v.lastElement());
    }
}
```

**输出:**

```
Geeksforgeeks
Java

```

**解释:**
函数–first element()返回向量中的第一个元素。
函数–LastElement()返回向量中的最后一个元素。

**6。以下程序的输出是什么**

```
import java.util.*;
class demo6 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        v.insertElementAt("Java", 0);
        System.out.println(v.indexOf("Geeksforgeeks"));
    }
}
```

**输出:**

```
1

```

**解释:**
函数–int indexOf(对象 E)返回元素 E 第一次出现的索引

**7。以下程序的输出是什么**

```
import java.util.*;
class demo7 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        v.addElement("Java");
        v.addElement("C++");
        v.addElement("C");
        v.addElement("Geeksforgeeks");
        System.out.println(v.indexOf("Geeksforgeeks", 2));
    }
}
```

**输出:**

```
4

```

**解释:**
函数–int indexOf(Object E，int start)–返回元素 E 在开始时或开始后第一次出现的索引。因此，“极客”的索引在索引“2”之后返回。

**8。以下程序的输出是什么**

```
import java.util.*;
class demo8 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        v.addElement("Java");
        Vector v1 = new Vector();
        v1 = (Vector)v.clone();
        System.out.println(v1.firstElement());
    }
}
```

**输出:**

```
Geeksforgeeks

```

**解释:**
函数–对象克隆( )返回调用向量的副本。
v1 是 v 的复制品，第一个元素是“极客”

**9。以下程序的输出是什么**

```
import java.util.*;
class demo9 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        Vector v1 = new Vector();
        v1 = (Vector)v.clone();
        System.out.println(v1.firstElement());

        v.insertElementAt("Java", 0);
        System.out.println(v1.firstElement());
    }
}
```

**输出:**

```
Geeksforgeeks
Geeksforgeeks

```

**解释:**
初始 v1.firstElement()返回向量 v1 的第一个元素。然后一个元素被添加到向量 v，但是它没有被添加到它的复制向量 v1。
因此，一旦克隆完成，新元素就不能添加到复制载体中。
所以向量 v 包含“Java”和“Geeksforgeeks”，向量 v1 只包含“Geeksforgeeks”。

**10。以下程序的输出是什么**

```
import java.util.*;
class demo10 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        Vector v1 = new Vector();
        v1 = (Vector)v.clone();
        v.insertElementAt("Java", 0);
        System.out.println(v1.contains("Java"));
    }
}
```

**输出:**

```
false

```

**解释:**
函数–布尔包含(对象 E)如果元素 E 包含在向量中，则返回“真”，否则返回假。

**11 时。以下程序的输出是什么**

```
import java.util.*;
class demo11 {
    public static void main(String[] args)
    {
        Vector v = new Vector(8);
        v.addElement("Geeksforgeeks");
        v.insertElementAt("Java", 0);
        String array[] = new String[8];
        v.copyInto(array);

        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**输出:**

```
Java
Geeksforgeeks
null
null
null
null
null
null

```

**解释:**
函数–void copy into(Object array[])将调用向量中包含的元素复制到‘array’指定的数组中。
现在数组只有 2 个元素“Java”和“Geeksforgeeks”，剩下的输出都是 null。

**12 时。以下程序的输出是什么**

```
import java.util.*;
class demo12 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        v.insertElementAt("Java", 0);
        v.removeAllElements();
        System.out.println(v.size());

        v.addElement("Geeksforgeeks");
        v.addElement("Java");
        v.removeElementAt(0);
        System.out.println(v.size());
    }
}
```

**输出:**

```
0
1

```

**解释:**
函数–void remove alilements()清空向量并移除向量的所有元素。此方法执行后，向量的大小为零。
函数–void removeElementAt(int index)删除“index”指定位置的元素。

**13。以下程序的输出是什么**

```
import java.util.*;
class demo13 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        v.addElement("Java");
        v.trimToSize();
        System.out.println(v.size());
        System.out.println(v.capacity());
    }
}
```

**输出:**

```
2
2

```

**解释:**
函数–void trimToSize()将向量的容量设置为它当前容纳的元素数量。

**14。以下程序的输出是什么**

```
import java.util.*;
class demo14 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        v.addElement("Java");
        v.trimToSize();

        v.addElement("C++");
        System.out.println(v.size());
        System.out.println(v.capacity());
    }
}
```

**输出:**

```
3
4

```

**说明:**
v.trimToSize()使大小和容量等于 2。
添加另一个元素后，大小变为 3，容量翻倍(默认情况下)即 4

**15。以下程序的输出是什么**

```
import java.util.*;
class demo15 {
    public static void main(String[] args)
    {
        Vector v = new Vector(30);
        v.addElement("Geeksforgeeks");
        v.addElement("Java");
        v.addElement("C++");
        v.addElement("C");
        System.out.println(v.toString());
        v.removeAllElements();
        System.out.println(v.toString());
    }
}
```

**输出:**

```
[Geeksforgeeks, Java, C++, C]
[]

```

**解释:**
函数–toString()返回向量的字符串等价物。
对 toString()函数的第一次调用显示向量内容的字符串等份 v.
移除所有元素后，向量变为空，因此对 toString()函数的第二次调用返回空字符串。