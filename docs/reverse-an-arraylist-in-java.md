# 在 Java 中反转数组列表

> 原文:[https://www.geeksforgeeks.org/reverse-an-arraylist-in-java/](https://www.geeksforgeeks.org/reverse-an-arraylist-in-java/)

假设你已经在 java 中浏览过[数组列表，并且知道数组列表。这篇文章包含了不同的反转数组列表的例子，如下所示:
**1。通过编写我们自己的函数(**使用额外的空间**):**RevArrayList 类中的 reverseArrayList()方法包含用整数对象反转数组列表的逻辑。此方法将数组列表作为参数，以相反的顺序遍历并将所有元素添加到新创建的数组列表中。最后返回反向数组列表。](https://www.geeksforgeeks.org/arraylist-in-java/) 

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for reversing an arraylist
import java.io.*;
import java.util.*;
class RevArrayList {

    // Takes an arraylist as a parameter and returns
    // a reversed arraylist
    public ArrayList<Integer> reverseArrayList(ArrayList<Integer> alist)
    {
        // Arraylist for storing reversed elements
        ArrayList<Integer> revArrayList = new ArrayList<Integer>();
        for (int i = alist.size() - 1; i >= 0; i--) {

            // Append the elements in reverse order
            revArrayList.add(alist.get(i));
        }

        // Return the reversed arraylist
        return revArrayList;
    }

    // Iterate through all the elements and print
    public void printElements(ArrayList<Integer> alist)
    {
        for (int i = 0; i < alist.size(); i++) {
            System.out.print(alist.get(i) + " ");
        }
    }
}

public class GFG {
    public static void main(String[] args)
    {
        RevArrayList obj = new RevArrayList();

        // Declaring arraylist without any initial size
        ArrayList<Integer> arrayli = new ArrayList<Integer>();

        // Appending elements at the end of the list
        arrayli.add(new Integer(1));
        arrayli.add(new Integer(2));
        arrayli.add(new Integer(3));
        arrayli.add(new Integer(4));
        System.out.print("Elements before reversing:");
        obj.printElements(arrayli);
        arrayli = obj.reverseArrayList(arrayli);
        System.out.print("\nElements after reversing:");
        obj.printElements(arrayli);
    }
}
```

**Output:** 

```
Elements before reversing:1 2 3 4 
Elements after reversing:4 3 2 1
```

**1。通过编写我们自己的函数(**而不使用额外的空间 **):** 在前面的例子中，数组列表被额外用于存储所有占用更多空间的反向元素。为了避免这种情况，可以使用相同的数组列表进行反转。
**逻辑:**
1。循环 n/2 次，其中“n”是数组列表中的元素数。
2。第一遍，交换第一个和第 n 个元素
3。在第二遍中，交换第二个和第(n-1)个元素，以此类推，直到到达数组列表的中间。
4。循环结束后返回数组列表。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for reversing an arraylist
import java.io.*;
import java.util.*;
class RevArrayList {

    // Takes an arraylist as a parameter and returns
    // a reversed arraylist
    public ArrayList<Integer> reverseArrayList(ArrayList<Integer> alist)
    {
        // Arraylist for storing reversed elements
        // this.revArrayList = alist;
        for (int i = 0; i < alist.size() / 2; i++) {
            Integer temp = alist.get(i);
            alist.set(i, alist.get(alist.size() - i - 1));
            alist.set(alist.size() - i - 1, temp);
        }

        // Return the reversed arraylist
        return alist;
    }

    // Iterate through all the elements and print
    public void printElements(ArrayList<Integer> alist)
    {
        for (int i = 0; i < alist.size(); i++) {
            System.out.print(alist.get(i) + " ");
        }
    }
}

public class GFG1 {
    public static void main(String[] args)
    {
        RevArrayList obj = new RevArrayList();

        // Declaring arraylist without any initial size
        ArrayList<Integer> arrayli = new ArrayList<Integer>();

        // Appending elements at the end of the list
        arrayli.add(new Integer(12));
        arrayli.add(new Integer(13));
        arrayli.add(new Integer(123));
        arrayli.add(new Integer(54));
        arrayli.add(new Integer(1));
        System.out.print("Elements before reversing: ");
        obj.printElements(arrayli);
        arrayli = obj.reverseArrayList(arrayli);
        System.out.print("\nElements after reversing: ");
        obj.printElements(arrayli);
    }
}
```

**Output:** 

```
Elements before reversing: 12 13 123 54 1 
Elements after reversing: 1 54 123 13 12
```