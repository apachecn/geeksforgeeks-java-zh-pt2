# Java 中的字符串数组

> 原文:[https://www.geeksforgeeks.org/string-arrays-in-java/](https://www.geeksforgeeks.org/string-arrays-in-java/)

在编程中，[数组](https://www.geeksforgeeks.org/array-data-structure/)是存储在连续存储单元中的同类数据的集合，每个数据都可以使用其索引来访问。

在 Java 编程语言中，我们有一个[字符串](https://www.geeksforgeeks.org/string-class-in-java/)数据类型。字符串只不过是一个表示字符值序列的对象。字符串在 java 中是不可变的。不可变意味着字符串不能在 java 中修改。

当我们在 Java 中创建一个 String 类型的数组时，在 Java 中称为 **String Array。**

要使用字符串数组，首先，我们需要声明并初始化它。有不止一种方法可以做到这一点。

#### 声明:

字符串数组可以在程序中声明为无大小或有大小。下面是相同的代码–

```java
String[] myString0; // without size
String[] myString1=new String[4]; //with size
```

在上面的代码中，我们声明了一个没有大小的字符串数组(myString0)和另一个大小为 4 的字符串数组(myString1)。我们可以用这两种方式在 java 中声明我们的 String 数组。

#### 初始化:

```java
//first method
String[] arr0=new String[]{"Apple","Banana","Orange"};

//second method
String[] arr1={"Apple","Banana","Orange"};

//third method
String[] arr2=new String[3];
arr2[0]="Apple";
arr2[1]="Banana";
arr2[2]="Orange";
```

在**第一种方法**中，我们在同一行声明值。A **第二种方法**是第一种方法的简称，在**最后一种方法**中，首先我们创建一个大小为的字符串数组，然后我们将数据存储到其中。

#### 迭代:

为了迭代字符串数组，我们可以使用循环语句。

## 爪哇

```java
// Java program to demonstrate the various
// methods to iterate over a string array 

public class GFG {
    public static void main(String[] args)
    {
        String[] arr = { "Apple", "Banana", "Orange" };

          // First method
        for (String i : arr) {
            System.out.print(i + " ");
        }
        System.out.println();

          // Second method
        for (int i = 0; i < arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
        System.out.println();

          // Third method
        int i = 0;
        while (i < arr.length) {
            System.out.print(arr[i] + " ");
            i++;
        }
        System.out.println();
    }
}
```

**输出**

```java
Apple Banana Orange 
Apple Banana Orange 
Apple Banana Orange 
```

一般来说，我们有三种方法迭代字符串数组。**第一种方法**是使用 for-each 循环。**第二种方法**使用简单的 for 循环，**第三种方法**使用 while 循环。您可以从[Java 中的数组迭代](https://www.geeksforgeeks.org/iterating-arrays-java/)中了解更多关于数组迭代的信息

#### 搜索:

为了从字符串数组中找到一个元素，我们可以使用一个简单的[线性搜索](https://www.geeksforgeeks.org/linear-search/)算法。这里的实现是一样的–

## Java

```java
// Java program to perform the searching
// operation on a string array

public class GFG {
    public static void main(String[] args)
    {
        String[] arr = { "Apple", "Banana", "Orange" };
        String key = "Banana";
        boolean flag = false;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == key) {
                System.out.println("Available at index "
                                   + i);
                flag = true;
            }
        }
        if (flag == false) {
            System.out.println("Not found");
        }
    }
}
```

**输出**

```java
Available at index 1
```