# 替换 Java 向量中的元素

> 原文:[https://www . geesforgeks . org/replacement-in-Java-vector/](https://www.geeksforgeeks.org/replacing-element-in-java-vector/)

要替换 Java Vector 中的元素，可以使用 **java.util.Vector** 类的 **set()** 方法。set()方法接受两个参数——需要替换的元素的索引和新元素。向量的索引从零开始。因此，要替换第一个元素，0 应该是作为参数传递的索引。

**申报:**T0】

**返回值:**

```
The element which is at the specified index
```

**异常抛出:**

```
IndexOutOfBoundsException 
when the index is out of range 
i.e, index < 0 or index >= size()
```

实现:

## Java

```
// Replacing Element in Java Vector
import java.util.Vector;
public class Sias {
    public static void main(String args[])
    {
        try {

            // create a instance vector
            Vector<Integer> vector = new Vector<>();

            // insert the values in vector
            vector.add(1);
            vector.add(2);
            vector.add(3);
            vector.add(4);
            vector.add(5);

            // display the vector
            System.out.println("original vector : "
                               + vector);

            // call set() and replace 2 index value
            vector.set(2, 10);

            // display vector after replacing value
            System.out.println("after replace the value : "
                               + vector);
            // call set() and replace 9th index value
            // which is exception as arrayoutofbound
            vector.set(9, 91);

            // display vector after replacing value
            System.out.println("after replace the value : "
                               + vector);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出**

```
original vector : [1, 2, 3, 4, 5]
after replace the value : [1, 2, 10, 4, 5]
java.lang.ArrayIndexOutOfBoundsException: Array index out of range: 9

```

**时间复杂度:** O(n)，其中 n 是向量的长度