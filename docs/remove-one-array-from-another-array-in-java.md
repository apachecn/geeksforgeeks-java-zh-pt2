# 在 Java 中从另一个数组中移除一个数组

> 原文:[https://www . geesforgeks . org/从另一个 java 数组中移除一个数组/](https://www.geeksforgeeks.org/remove-one-array-from-another-array-in-java/)

为了在 java 中从另一个数组中移除一个数组，我们将使用 **removeAll()** 方法。如果我们从数组 2 中调用 remove all()函数并将数组 1 作为参数，这将从数组 2 中移除数组 1 的所有元素。

**语法:**

```
public boolean removeAll(Collection c)
```

**参数:**该方法将集合 c 作为包含要从该列表中移除的元素的参数。

**返回值:**如果该列表因调用而改变，则该方法返回真。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Remove One Array From Another Array

import java.util.ArrayList;
import java.util.List;

class GFG {
    public static void main(String[] args)
    {

        // creating first array
        List<Integer> firstList = new ArrayList<>();

        // creating second array
        List<Integer> secondList = new ArrayList<>();

        // adding elements in first array
        firstList.add(100);
        firstList.add(200);
        firstList.add(300);
        firstList.add(400);
        firstList.add(500);
        firstList.add(600);

        // adding elements in second array
        secondList.add(300);
        secondList.add(500);

        // displaying element of first array
        System.out.println("elements in first array "
                           + firstList);

        // displaying element of second array
        System.out.println("elements in second array "
                           + secondList);

        // removing elements from firstarray
        firstList.removeAll(secondList);

        // displaying elements of first array
        // after removing elements of second array
        // from first array
        System.out.println("first array after removing second array from first array\n"
            + firstList);
    }
}
```

**Output**

```
elements in first array [100, 200, 300, 400, 500, 600]
elements in second array [300, 500]
first array after removing second array from first array
[100, 200, 400, 600]

```

**例 2:**

在这个例子中，我们将使用用户定义的类，而不是使用 java 的包装类，但是为了使用用户定义的类，我们需要重写 equals()和 hashCode()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Remove One Array From Another Array

import java.io.*;
import java.util.*;

class friendsDetail {

    // class field
    private String name;
    private String nickName;

    // parameterised constructor
    public friendsDetail(String name, String nickName)
    {
        this.name = name;
        this.nickName = nickName;
    }

    // getter for name
    public String getName() { return name; }

    // setter for name
    public void setName(String name) { this.name = name; }

    // getter for nickname
    public String getnickName() { return nickName; }

    // setter for nickname
    public void setNickName(int id)
    {
        this.nickName = nickName;
    }

    @Override public boolean equals(Object o)
    {

        if (this == o)
            return true;

        if (!(o instanceof friendsDetail))
            return false;

        friendsDetail that = (friendsDetail)o;

        return Objects.equals(getName(), that.getName())
            && Objects.equals(nickName, that.nickName);
    }

    @Override public int hashCode()
    {
        return Objects.hash(getName(), nickName);
    }

    // overriding toString method
    public String toString()
    {
        // return super.toString();
        return "(" + this.getName() + ":"
                        + this.getnickName() + ")";
    }
}
public class GFG {
    public static void main(String[] args)
    {
        ArrayList<friendsDetail> firstArrayList = new ArrayList<>();

        System.out.println("Our First ArrayList\n");

        // adding elements to first ArrayList
        firstArrayList.add(new friendsDetail("Amit", "Ghulla"));
        firstArrayList.add(new friendsDetail("Yashdeep", "Dopa"));
        firstArrayList.add(new friendsDetail("Jyoti", "Kauwa"));
        firstArrayList.add(new friendsDetail("Suraj", "Bhindi"));
        firstArrayList.add(new friendsDetail("Himanshu", "Lalten"));
        firstArrayList.add(new friendsDetail("Sarthak", "Nagin"));
        firstArrayList.add(new friendsDetail("Tsering", "Battak"));
        firstArrayList.add(new friendsDetail("Abhishek", "Liquid"));

        // Displaying output of first array using enhanced
        // for loop
        for (friendsDetail friend : firstArrayList) {
            System.out.println(friend);
        }

        ArrayList<friendsDetail> secondArrayList = new ArrayList<>();

        System.out.println("\nOur Second ArrayList\n");

        // adding elements to second ArrayList.
        secondArrayList.add(new friendsDetail("Amit", "Ghulla"));
        secondArrayList.add(new friendsDetail("Jyoti", "Kauwa"));
        secondArrayList.add(new friendsDetail("Himanshu", "Lalten"));
        secondArrayList.add(new friendsDetail("Abhishek", "Liquid"));

        // Displaying output of original array using
        // enhanced for loop
        for (friendsDetail friend : secondArrayList) {
            System.out.println(friend);
        }

        // removing second array elements from first array
        firstArrayList.removeAll(secondArrayList);

        System.out.println(
          "\nFirst array after removing second array from first array\n");

        // Displaying first array after removing second
        // array elements from first array
        for (friendsDetail friend : firstArrayList) {
            System.out.println(friend);
        }
    }
}
```

**Output**

```
Our First ArrayList

(Amit:Ghulla)
(Yashdeep:Dopa)
(Jyoti:Kauwa)
(Suraj:Bhindi)
(Himanshu:Lalten)
(Sarthak:Nagin)
(Tsering:Battak)
(Abhishek:Liquid)

Our Second ArrayList

(Amit:Ghulla)
(Jyoti:Kauwa)
(Himanshu:Lalten)
(Abhishek:Liquid)

First array after removing second array from first array

(Yashdeep:Dopa)
(Suraj:Bhindi)
(Sarthak:Nagin)
(Tsering:Battak)

```