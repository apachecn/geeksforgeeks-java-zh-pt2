# Java 中 StringBuffer append()方法，示例

> 原文:[https://www . geesforgeks . org/stringbuffer-append-method-in-Java-with-examples/](https://www.geeksforgeeks.org/stringbuffer-append-method-in-java-with-examples/)

先决条件:[Java 中的 StringBuffer 类](https://www.geeksforgeeks.org/stringbuffer-class-in-java/)
**Java . lang . StringBuffer . append()**方法用于将某个参数的字符串表示形式追加到序列中。append()方法有 13 种使用方式/形式:

1.  **StringBuffer append(*boolean a*) :**The java.lang.StringBuffer.append(*boolean a*) is an inbuilt method in Java which is used to append the string representation of the boolean argument to a given sequence.

    **语法:**

    ```
    public StringBuffer append(*boolean a*)
    ```

    **参数:**此方法接受布尔类型的单个参数 *a* ，并引用要追加的布尔值。

    **返回值:**该方法返回对此对象的引用。

    **示例:**

    ```
    Input: 
    string_buffer = "I love my Country" 
    boolean a = true

    Output: I love my Country true

    ```

    下面的程序说明了 java.lang.StringBuffer.append()方法:

    ```
    // Java program to illustrate the
    // StringBuffer append(boolean a)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            StringBuffer sbf1 = new StringBuffer("We are geeks and its really ");
            System.out.println("Input: " + sbf1);

            // Appending the boolean value
            sbf1.append(true);
            System.out.println("Output: " + sbf1);

            System.out.println();

            StringBuffer sbf2 = new StringBuffer("We are lost - ");
            System.out.println("Input: " + sbf2);

            // Appending the boolean value
            sbf2.append(false);
            System.out.println("Output: " + sbf2);
        }
    }
    ```

    **Output:**

    ```
    Input: We are geeks and its really 
    Output: We are geeks and its really true

    Input: We are lost - 
    Output: We are lost - false

    ```

2.  **java.lang.StringBuffer.append(*char a*) :** This is an inbuilt method that appends the string representation of the char argument to the given sequence. The char argument is appended to the contents of this StringBuffer sequence.

    **语法:**

    ```
    public StringBuffer append(*char a*)
    ```

    **参数:**该方法接受单个参数 *a* ，这是字符串表示将被追加的字符值。

    **返回值:**该方法在执行追加操作后返回一个字符串对象。
    **例:**

    ```
    Input :
    StringBuffer = I love my Country 
    char a = A

    Output: I love my Country A
    ```

    下面的程序说明了 Java . lang . StringBuffer . append(char a)方法。

    ```
    // Java program to illustrate the
    // java.lang.StringBuffer.append(char a)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {
            System.out.println("We are geeks and its really ");
            StringBuffer sbf = new StringBuffer("We are geeks and its");

            /* Here it appends the char argument as
             string to the string buffer */
            sbf.append('M');
            System.out.println("Result after appending = " + sbf);

            System.out.println("We are lost -");
            sbf = new StringBuffer("We are lost -");

            /* Here it appends the char argument as
             string to the string buffer */
            sbf.append('&');
            System.out.println("Result after appending = " + sbf);
        }
    }
    ```

    **Output:**

    ```
    We are geeks and its really 
    Result after appending = We are geeks and itsM
    We are lost -
    Result after appending = We are lost -&

    ```

3.  **StringBuffer append(*char[] astr*):** The java.lang.StringBuffer.append(*char[] astr*) is the inbuilt method which appends the string representation of the char array argument to this StringBuffer sequence.

    **语法:**

    ```
    public StringBuffer append(*char[] astr*)
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

    下面的程序说明了 Java . lang . stringbuffer . append(*char[]astr*)方法:

    ```
    // Java program to illustrate the
    // java.lang.StringBuffer.append(<em>char[] astr</em>)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            System.out.println("We are geeks and its really ");
            StringBuffer sbf = new StringBuffer("We are geeks and its ");

            // Char array
            char[] astr = new char[] { 'G', 'E', 'E', 'k', 'S' };

            /* Here it appends string representation of char array 
            argument to this string buffer */
            sbf.append(astr);
            System.out.println("Result after appending = " + sbf);

            System.out.println("We are lost -");
            sbf = new StringBuffer("We are lost -");

            // Char array
            astr = new char[] { 'a', 'b', 'c', 'd' };

            /* Here it appends string representation of char array argument to
            argument to this string buffer */
            sbf.append(astr);
            System.out.println("Result after appending = " + sbf);
        }
    }
    ```

    **Output:**

    ```
    We are geeks and its really 
    Result after appending = We are geeks and its GEEkS
    We are lost -
    Result after appending = We are lost -abcd

    ```

4.  **StringBuffer append(*char[] cstr, int iset, int ilength*) :** This method appends the string representation of a subarray of the char array argument to this sequence. The Characters of the char array cstr, starting at index iset, are appended, in order, to the contents of this sequence. The length of this sequence increases by the value of ilength.

    **语法:**

    ```
    public StringBuffer append(*char[] cstr, int iset, int ilenght*)
    ```

    **参数:**该方法接受三个参数:

    *   *CSTR*–这是指 Char 序列。
    *   *iset*–这是指要追加的第一个字符的索引。
    *   *ileng ht*–这是指要追加的字符数。

    **返回值:**该方法在执行追加操作后返回一个字符串对象。
    下面的程序说明了 Java . lang . stringbuffer . append(char[]CSTR，int iset，int ilength)方法。

    ```
    // Java program to illustrate the
    // java.lang.StringBuffer append(char[] cstr, int iset, int ilength)
    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            StringBuffer sb = new StringBuffer("Geeks");
            System.out.println(" String buffer  before = " + sb);

            char[] cstr = new char[] { 'f', 'o', 'r', 'G', 'e', 'e', 'k', 's',
                                       'b', 'e', 'a', 'g', 'e', 'e', 'k' };

            /* appends the string representation of char array argument to this
          string buffer with offset initially at index 0 and length as 8 */
            sb.append(cstr, 0, 8);

            // Print the string buffer after appending
            System.out.println("After appending string buffer = " + sb);
        }
    }
    ```

    **Output:**

    ```
    String buffer  before = Geeks
    After appending string buffer = GeeksforGeeks

    ```