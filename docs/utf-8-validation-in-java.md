# Java 中的 UTF-8 验证

> 原文:[https://www.geeksforgeeks.org/utf-8-validation-in-java/](https://www.geeksforgeeks.org/utf-8-validation-in-java/)

**UTF-8** 中的字符长度可以是 1 到 4 个字节，遵循以下规则:

1.  对于 1 字节字符，第一位是 0，后面是其 Unicode 代码。
2.  对于 n 字节字符，前 n 位都是 1，n+1 位是 0，随后是 n-1 字节，最高有效的 2 位是 10。

**这就是 UTF-8 编码的工作原理:**

```java
  Char. number range   |        UTF-8 octet sequence
      (hexadecimal)    |              (binary)
   --------------------+---------------------------------------------
   0000 0000-0000 007F | 0xxxxxxx
   0000 0080-0000 07FF | 110xxxxx 10xxxxxx
   0000 0800-0000 FFFF | 1110xxxx 10xxxxxx 10xxxxxx
   0001 0000-0010 FFFF | 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx
```

**示例:**

给定一个表示数据的整数数组，返回它是否是有效的 UTF-8 编码。

输入是整数数组。每个整数只有最低有效的 8 位用于存储数据。这意味着每个整数只代表 1 个字节的数据。

> **数据**=【235，140，4】，表示八位字节序列:11101011 10001100 00000100。
> 
> **返回假。**
> 
> 前 3 位都是 1，第 4 位是 0，表示它是一个 3 字节的字符。
> 
> 下一个字节是以 10 开头的延续字节，这是正确的。
> 
> 但是第二个延续字节不是以 10 开头，所以是无效的。
> 
> ———————————————————————————————–
> 
> **数据**=【197，130，1】，代表八进制序列:11000101 10000010 00000001。
> 
> **还真。**
> 
> 对于 2 字节字符后跟 1 字节字符**，这是一个有效的 utf-8 编码。**

**方法:**只要数组中的每个字节都是正确的类型，它就是有效的 UTF-8 编码。**T3】**

*   从索引 0 开始，确定每个字节的类型并检查其有效性。
*   有效字节类型有五种:0**、10**、110**、1110**和 11110**
*   给他们键入数字，0，1，2，3，4，它们是从左数第一个 0 的索引。
*   所以，第一个 0 的索引决定了字节类型。
*   如果一个字节属于其中之一:如果它是类型 0，如果它是类型 2 或 3 或 4，则继续，检查下面的 1、2 和 3 字节是否是类型 1。
*   如果不是，返回 false 否则，如果一个字节是类型 1 或者不是有效类型，返回 false。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to check whether the data
// is a valid UTF-8 encoding

import java.io.*;
import java.util.*;

class Sol {

    private int[] masks = { 128, 64, 32, 16, 8 };

    public boolean validUtf8(int[] data)
    {
        int len = data.length;

        // for each value in the data array we have to take
        // the "and" with the masks array
        for (int i = 0; i < len; i++) {
            int curr = data[i];

            // method to check the array if the
            // and with the num and masks array is
            // 0 then return true
            int type = getType(curr);

            if (type == 0) {
                continue;
            }

            else if (type > 1 && i + type <= len)
            {
                while (type-- > 1) 
                {
                    if (getType(data[++i]) != 1)
                    {
                        return false;
                    }
                }
            }
            else {
                return false;
            }
        }
        return true;
    }

    // method to check the type
    public int getType(int num)
    {
        for (int i = 0; i < 5; i++) {

            // checking the each input
            if ((masks[i] & num) == 0) {
                return i;
            }
        }

        return -1;
    }
}

class GFG {
    public static void main(String[] args)
    {
        Sol st = new Sol();
        int[] arr = { 197, 130, 1 };

        boolean res = st.validUtf8(arr);
        System.out.println(res);
    }
}
```

**Output**

```java
true
```

*   **时间复杂度:** O(n)
*   **空间复杂度:** O(1)