# Java 中 StringBuilder append()方法示例

> 原文:[https://www . geeksforgeeks . org/stringbuilder-append-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuilder-append-method-in-java-with-examples/)

**Java . lang . StringBuilder . append()**方法用于将某个参数的字符串表示形式追加到序列中。有 13 种方式/形式可以通过传递各种类型的参数来使用 append()方法:

1.  **StringBuilder append(*boolean a*) :**The java.lang.StringBuilder.append(*boolean a*) is an inbuilt method in Java which is used to append the string representation of the boolean argument to a given sequence.

    **语法:**

    ```
    public StringBuilder append(*boolean a*)
    ```

    **参数:**此方法接受布尔类型的单个参数 *a* ，并引用要追加的布尔值。

    **返回值:**该方法返回对此对象的引用。

    **示例:**

    ```
    Input: 
    string_buffer = "We are Indians" 
    boolean a = true

    Output: We are Indians true

    ```

    下面的程序说明了 java.lang.StringBuilder.append()方法:

    ```
    // Java program to illustrate the
    // StringBuilder append(boolean a)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            StringBuilder sb1 = new 
                          StringBuilder("Welcome to Geeksforgeeks ");
            System.out.println("Input: " + sb1);

            // Appending the boolean value
            sb1.append(true);
            System.out.println("Output: " + sb1);

            System.out.println();

            StringBuilder sb2 = new StringBuilder("We fail- ");
            System.out.println("Input: " + sb2);

            // Appending the boolean value
            sb2.append(false);
            System.out.println("Output: " + sb2);
        }
    }
    ```

    **Output:**

    ```
    Input: Welcome to Geeksforgeeks 
    Output: Welcome to Geeksforgeeks true

    Input: We fail- 
    Output: We fail- false

    ```

2.  **java.lang.StringBuilder.append(*char a*):** This is an inbuilt method in Java which is used to append the string representation of the char argument to the given sequence. The char argument is appended to the contents of this StringBuilder sequence.

    **语法:**

    ```
    public StringBuilder append(*char a*)
    ```

    **参数:**该方法接受单个参数 *a* ，这是字符串表示将被追加的字符值。

    **返回值:**该方法在执行追加操作后返回一个字符串对象。
    **例:**

    ```
    Input :
    StringBuilder = I love my Country 
    char a = A

    Output: I love my Country A
    ```

    下面的程序说明了 Java . lang . StringBuilder . append(char a)方法。

    ```
    // Java program to illustrate the
    // java.lang.StringBuilder.append(char a)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            StringBuilder sbf = new 
                           StringBuilder("Welcome geeks!");
                    System.out.println( sbf);

            /* Here it appends the char argument as
            string to the StringBuilder */
            sbf.append('T');
            System.out.println("Result after"+
                                     " appending = " + sbf);

            sbf = new StringBuilder("hello world-");
                    System.out.println(sbf);
            /* Here it appends the char argument as
            string to the String Builder */
            sbf.append('#');
            System.out.println("Result after appending = " 
                                                             + sbf);
        }
    }
    ```

    **Output:**

    ```
    Welcome geeks!
    Result after appending = Welcome geeks!T
    hello world-
    Result after appending = hello world-#

    ```

3.  **StringBuilder append(*char[] astr*):** The java.lang.StringBuilder.append(*char[] astr*) is the inbuilt method which appends the string representation of the char array argument to this StringBuilder sequence.

    **语法:**

    ```
    public StringBuilder append(*char[] astr*)
    ```

    **参数:**该方法接受单个参数*和*，它们是字符串表示将被附加的字符序列。

    **返回值:**该方法在执行追加操作后返回一个字符串对象。
    **例:**

    ```
    Input :
    StringBuffer  = *I love my Country  * 
    char[] astr = *'I', 'N', 'D', 'I', 'A'*

    Output: I love my Country INDIA

    ```

    下面的程序说明了 Java . lang . stringbuilder . append(*char[]astr*)方法:

    ```
    // Java program to illustrate the
    // java.lang.StringBuilder.append(<em>char[] astr</em>)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            StringBuilder sbf = new 
                          StringBuilder("We are geeks  ");
            System.out.println(sbf);

            // Char array
            char[] astr = new char[] 
                              { 'G', 'E', 'E', 'k', 'S' };

            /* Appends string representation of char
                       array to this String Builder */
            sbf.append(astr);
        System.out.println("Result after"+
                                " appending = " + sbf);

            sbf = new StringBuilder("We are  -");
                    System.out.println(sbf);

            // Char array
            astr = new char[] { 'a', 'b', 'c', 'd' };

            /* Appends string representation of char 
                       array to this StringBuilder */
            sbf.append(astr);
            System.out.println("Result after appending = " + sbf);
        }
    }
    ```

    **Output:**

    ```
    We are geeks  
    Result after appending = We are geeks  GEEkS
    We are  -
    Result after appending = We are  -abcd

    ```

4.  **StringBuilder append(*char[] cstr, int iset, int ilength*) :** This method appends the string representation of a subarray of the char array argument to this sequence. The Characters of the char array cstr, starting at index iset, are appended, in order, to the contents of this sequence. The length of this sequence increases by the value of ilength.

    **语法:**

    ```
    public StringBuilder append(*char[] cstr, int iset, int ilenght*)
    ```

    **参数:**该方法接受三个参数:

    *   *CSTR*–这是指 Char 序列。
    *   *iset*–这是指要追加的第一个字符的索引。
    *   *ileng ht*–这是指要追加的字符数。

    **返回值:**该方法在执行追加操作后返回一个字符串对象。
    下面的程序说明了 Java . lang . stringbuilder . append(char[]CSTR，int iset，int ilength)方法。

    ```
    // Java program to illustrate the
    // append(char[] cstr, int iset, int ilength)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            StringBuilder sb = new 
                                  StringBuilder("Geeks");
            System.out.println("String Builder "+
                                       "before = " + sb);

            char[] cstr = new char[] 
              { 'f', 'o', 'r', 'G', 'e', 'e', 'k', 's','q','q' };

            /* appends the string representation of char array 
               argument to this String Builder with offset initially 
               at index 0 and length as 8 */
            sb.append(cstr, 0, 8);

            // Print the String Builder after appending
            System.out.println("After appending String Builder = " + sb);
        }
    }
    ```

    **Output:**

    ```
    String Builder before = Geeks
    After appending String Builder = GeeksforGeeks

    ```