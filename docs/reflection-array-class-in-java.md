# Java 中的反射数组类

> 原文:[https://www . geesforgeks . org/reflection-array-class-in-Java/](https://www.geeksforgeeks.org/reflection-array-class-in-java/)

**java.lang.reflect 包**中的**数组**类是**Java reflect**的一部分。这个类提供了动态创建和访问 Java 数组的静态方法。它是最终类，这意味着它不能被实例化或更改。类名本身只能使用这个类的方法。

[**java.util.Arrays 类**](https://www.geeksforgeeks.org/array-class-in-java/) 包含各种操作数组的方法(如排序和搜索)，而这个 **java.lang.reflect.Array 类**提供了动态创建和访问 java 数组的静态方法。这个数组类保持数组的类型安全。

#### **等级体系**

```
java.lang.Object
 ↳ java.lang.reflect.Array
```

#### **班级申报**

```
public final class Array extends Object
```

#### **使用数组的语法**

```
Array.<function name>;
```

### **Java 中反射数组类中的方法**

<figure class="table">

| 南号码 | 方法 | 描述 |
| --- | --- | --- |
| **1** | [**对象获取(对象数组，int 索引)**](https://www.geeksforgeeks.org/array-get-method-in-java/) | 此方法返回指定数组对象中索引组件的值。 |
| **2** | [**布尔 getBoolean(对象数组，int 索引)**](https://www.geeksforgeeks.org/array-getboolean-method-in-java/) | 此方法以布尔值形式返回指定数组对象中索引组件的值。 |
| **3** | [字节(对象数组、int 索引)T3](https://www.geeksforgeeks.org/array-getbyte-method-in-java/) | 此方法以字节形式返回指定数组对象中索引组件的值。 |
| **4** | [**char getChar(对象数组，int 索引)**](https://www.geeksforgeeks.org/array-getchar-method-in-java/) | 此方法以字符形式返回指定数组对象中索引组件的值。 |
| **5** | [**double getDouble(对象数组，int index)**](https://www.geeksforgeeks.org/array-getdouble-method-in-java/) | 此方法以双精度形式返回指定数组对象中索引组件的值。 |
| **6** | [**float getFloat(对象数组，int 索引)**](https://www.geeksforgeeks.org/array-getfloat-method-in-java/) | 此方法以浮点形式返回指定数组对象中索引组件的值。 |
| **7** | [**int getInt(对象数组，int index)**](https://www.geeksforgeeks.org/array-getint-method-in-java/) | 此方法以 int 形式返回指定数组对象中索引组件的值。 |
| **8** | **int getLength(对象数组)** | 此方法以 int 形式返回指定数组对象的长度。 |
| **9** | [**长 getLong(对象数组，int 索引)**](https://www.geeksforgeeks.org/array-getlong-method-in-java/) | 此方法将指定数组对象中索引组件的值作为长整型返回。 |
| **10** | [**短 getShort(对象数组，int 索引)**](https://www.geeksforgeeks.org/array-getshort-method-in-java/) | 此方法将指定数组对象中索引组件的值作为短整型返回。 |
| **11** | **对象新实例(类< E >组件类型，整数长度)** | 此方法创建具有指定组件类型和长度的新数组。 |
| **12** | **对象新实例(类< E >组件类型，int…维度)** | 此方法创建具有指定组件类型和维度的新数组。 |
| **13** | [**虚空集(对象数组、int 索引、对象值)**](https://www.geeksforgeeks.org/array-set-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的新值。 |
| **14** | [**空集布尔(对象数组，int 索引，布尔 z)**](https://www.geeksforgeeks.org/array-setboolean-method-in-java-with-examples/) | 此方法将指定数组对象的索引组件的值设置为指定的布尔值。 |
| **15** | [**void setByte(对象数组，int 索引，字节 b)**](https://www.geeksforgeeks.org/array-setbyte-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的字节值。 |
| **16** | [**void setChar(对象数组，int 索引，char c)**](https://www.geeksforgeeks.org/array-setchar-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的字符值。 |
| **17** | [**虚空集双(对象数组，int 索引，double d)**](https://www.geeksforgeeks.org/array-setdouble-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的双精度值。 |
| **18** | [**void setFloat(对象数组，int index，float f)**](https://www.geeksforgeeks.org/array-setfloat-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的浮点值。 |
| **19** | [**void setInt(对象数组，Int 索引，int i)**](https://www.geeksforgeeks.org/array-setint-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的 int 值。 |
| **20** | [**void setLong(对象数组，int index，long l)**](https://www.geeksforgeeks.org/array-setlong-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的长值。 |
| **21** | [**空集短(对象数组，int 索引，短 s)**](https://www.geeksforgeeks.org/array-setshort-method-in-java/) | 此方法将指定数组对象的索引组件的值设置为指定的短值。 |

</figure>

### 如何使用 java.lang.util.reflect.Array 类创建数组？

使用**反射创建阵列。阵**类不同于通常的方式。创建这样一个数组的过程如下:

*   获取要创建的数组的大小
*   要创建一个数组(比如 X 类)，使用 array 类的 newInstance()方法将 X 类作为数组的类型和数组的大小作为参数传递。

**语法:**

```
X[] arrayOfXType = (X[]) Array.newInstance(X.class, size);
```

其中 X 将被数组的类型替换，如 int、double 等。

*   此方法返回给定大小的对象数组，然后转换为所需的 X[]类型。
*   因此，已经创建了所需的 X 类型数组。

下面是使用 array 类创建大小为 5 的整数数组的示例:

**示例:**要创建大小为 5 的整数数组:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to create an integer array of size 5,
// using the Array class:

import java.lang.reflect.Array;
import java.util.Arrays;

public class GfG {
    public static void main(String[] args)
    {

        // Get the size of the array
        int sizeOfArray = 5;

        // Create an integer array
        // using reflect.Array class
        // This is done using the newInstance() method

        int[] intArray = (int[])Array.newInstance(
            int.class, sizeOfArray);

        // Printing the Array content
        System.out.println(Arrays.toString(intArray));
    }
}
```

**Output**

```
[0, 0, 0, 0, 0]
```

### 如何使用 java.lang.util.reflect.Array 类在数组中添加元素？

就像创建数组一样，使用 reflect 在数组中添加元素。数组类也不同于通常的方式。在这样的数组中添加元素的过程如下:

*   获取要添加的元素的值。
*   获取要添加元素的索引。
*   要在数组中添加一个元素(比如 X 类)，使用 array 类的 setX()方法，其中 X 将被数组的类型替换，比如 setInt()，setDouble()，等等。在下面的语法中，此方法将 X[]作为第一个参数，将添加元素的索引作为第二个参数，将元素作为第三个参数。

**语法:**

```
Array.setX(X[], indexOfInsertion, elementToBeInserted);
```

其中 X 将被数组的类型替换，如 int、double 等。

*   此方法在此数组中的指定索引处插入元素。
*   因此，所需的元素已经插入到数组中。

下面是使用 array 类将元素添加到整数数组中的示例:

**示例:**要将元素添加到整数数组中:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to add an element into an integer array,
// using the Array class:

import java.lang.reflect.Array;
import java.util.Arrays;

public class GfG {
    public static void main(String[] args)
    {

        // Get the size of the array
        int sizeOfArray = 3;

        // Create an integer array
        // using reflect.Array class
        // This is done using the newInstance() method
        int[] intArray = (int[])Array.newInstance(
            int.class, sizeOfArray);

        // Add elements into the array
        // This is done using the setInt() method
        Array.setInt(intArray, 0, 10);
        Array.setInt(intArray, 1, 20);
        Array.setInt(intArray, 2, 30);

        // Printing the Array content
        System.out.println(Arrays.toString(intArray));
    }
}
```

**Output**

```
[10, 20, 30]
```

### 如何使用 java.lang.util.reflect.Array 类检索数组中的元素？

就像创建数组一样，使用 reflect 检索数组中的元素。数组类也不同于通常的方式。在这样的数组中检索元素的过程如下:

*   获取要检索元素的索引。
*   要检索数组中的元素(比如 X 类)，请使用 array 类的 getX()方法，其中 X 将被数组的类型替换，如 getInt()、getDouble()等。在下面的语法中，此方法将 X[]作为第一个参数，将检索元素的索引作为第二个参数。

**语法:**

```
Array.getX(X[], indexOfRetrieval);
```

其中 X 将被数组的类型替换，如 int、double 等。

*   此方法从此数组中检索指定索引处的元素。
*   因此，已从数组中检索到所需的元素。

下面是使用 array 类从整数数组中检索元素的示例:

**示例:**要从整数数组中检索元素:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to retrieve an element from an integer array,
// using the Array class:

import java.lang.reflect.Array;
import java.util.Arrays;

public class GfG {
    public static void main(String[] args)
    {

        // Get the size of the array
        int sizeOfArray = 3;

        // Create an integer array
        // using reflect.Array class
        // This is done using the newInstance() method
        int[] intArray = (int[])Array.newInstance(
            int.class, sizeOfArray);

        // Add elements from the array
        // This is done using the getInt() method
        Array.setInt(intArray, 0, 10);
        Array.setInt(intArray, 1, 20);
        Array.setInt(intArray, 2, 30);

        // Printing the Array content
        System.out.println(Arrays.toString(intArray));

        // Retrieve elements from the array
        // This is done using the getInt() method
        System.out.println("Element at index 0: "
                           + Array.getInt(intArray, 0));
        System.out.println("Element at index 1: "
                           + Array.getInt(intArray, 1));
        System.out.println("Element at index 2: "
                           + Array.getInt(intArray, 2));
    }
}
```

**Output**

```
[10, 20, 30]
Element at index 0: 10
Element at index 1: 20
Element at index 2: 30
```