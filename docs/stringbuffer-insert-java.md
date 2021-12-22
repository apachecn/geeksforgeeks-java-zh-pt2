# StringBuffer 在 Java 中插入()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/string buffer-insert-Java/

StringBuffer.insert()方法将给定数据类型的字符串表示形式插入到 [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) 中的给定位置。

**语法:**

```java
 str.insert(int position,  char x);
 str.insert(int position,  boolean x);
 str.insert(int position,  char[] x);
 str.insert(int position, float x);
 str.insert(int position, double x);
 str.insert(int position, long x);
 str.insert(int position, int x);

position is the index in string where
we need to insert.

```

**返回:**

```java
This method returns a reference to this object.
```

例外:

```java
The position argument must be greater
than or equal to 0, and less than 
or equal to the length of this string.

```

**布尔输入**

```java
// Java program to demonstrate StringBuffer insert
// for boolean input.  
import java.lang.*;

public class GFG {
    public static void main(String[] args)
    {
        StringBuffer str = 
             new StringBuffer("geeks for geeks");
        System.out.println("string = " + str);

        // insert boolean value at offset 8
        str.insert(8, true);

        // prints stringbuffer after insertion
        System.out.print("After insertion = ");
        System.out.println(str.toString());
    }
}
```

**Output:**

```java
string = geeks for geeks
After insertion = geeks fotruer geeks

```

**字符输入**

```java
// Java program to demonstrate StringBuffer insert
// for char input.  
import java.lang.*;

public class GFG {
    public static void main(String[] args)
    {
        StringBuffer str = 
           new StringBuffer("geeks for geeks");
        System.out.println("string = " + str);

        // insert boolean value at offset 8
        str.insert(8, 'p');

        // prints stringbuffer after insertion
        System.out.print("After insertion = ");
        System.out.println(str.toString());
    }
}
```

**Output:**

```java
string = geeks for geeks
After insertion = geeks fopr geeks

```

**字符数组输入**

```java
// Java program to demonstrate StringBuffer insert
// for char array input.  
import java.lang.*;

public class GFG {
    public static void main(String[] args)
    {
        StringBuffer str = 
               new StringBuffer("geeks for geeks");
        System.out.println("string = " + str);

        // character array to be inserted
        char cArr[] = { 'p', 'a', 'w', 'a', 'n' };

        // insert character array at offset 9
        str.insert(8, cArr);

        // prints stringbuffer after insertion
        System.out.print("After insertion = ");
        System.out.println(str.toString());
    }
}
```

**Output:**

```java
string = geeks for geeks
After insertion = geeks fopawanr geeks

```

**浮动输入**

```java
// Java program to demonstrate StringBuffer insert
// for float input.
import java.lang.*;

public class GFG 
{
    public static void main(String[] args)
    {
        StringBuffer str =
            new StringBuffer("geeks for geeks");
        System.out.println("string = " + str);

        // insert float value at offset 3
        str.insert(8, 41.35f);

        // prints stringbuffer after insertion
        System.out.print("After insertion = ");
        System.out.println(str.toString());
   }      
}
```

**Output:**

```java
string = geeks for geeks
After insertion = geeks fo41.35r geeks

```

**双输入**

```java
// Java program to demonstrate StringBuffer insert
// for double input.
import java.lang.*;

public class GFG 
{
    public static void main(String[] args)
    {
        StringBuffer str = 
           new StringBuffer("geeks for geeks");
        System.out.println("string = " + str);

        // insert float value at offset 3
        str.insert(8, 41.35d);

        // prints stringbuffer after insertion
        System.out.print("After insertion = ");
        System.out.println(str.toString());
   }      
}
```

**Output:**

```java
string = geeks for geeks
After insertion = geeks fo41.35r geeks

```

**长输入**

```java
// Java program to demonstrate StringBuffer insert
// for Long input.
import java.lang.*;

public class GFG 
{
    public static void main(String[] args)
    {
        StringBuffer str = new StringBuffer("geeks for geeks");
        System.out.println("string = " + str);

        // insert float value at offset 3
        str.insert(8, 546986L);

        // prints stringbuffer after insertion
        System.out.print("After insertion = ");
        System.out.println(str.toString());
   }      
}
```

**Output:**

```java
string = geeks for geeks
After insertion = geeks fo546986r geeks

```

**内部输入**

```java
// Java program to demonstrate StringBuffer insert
// for Int input.
import java.lang.*;

public class GFG 
{
    public static void main(String[] args)
    {
        StringBuffer str = 
            new StringBuffer("geeks for geeks");
        System.out.println("string = " + str);

        // insert float value at offset 8
        int x = 10;
        str.insert(8, x);

        // prints stringbuffer after insertion
        System.out.print("After insertion = ");
        System.out.println(str.toString());
   }      
}
```

**Output:**

```java
string = geeks for geeks
After insertion = geeks fo10r geeks

```