# Java 中可抛出的 getLocalizedMessage()方法，示例

> 原文:[https://www . geesforgeks . org/throwable-get localized message-method-in-Java-with-examples/](https://www.geeksforgeeks.org/throwable-getlocalizedmessage-method-in-java-with-examples/)

**可抛出类**的 **getLocalizedMessage()** 方法用于在发生异常时获取可抛出对象的特定于区域的描述。它帮助我们根据本地特定消息修改可投掷对象的描述。对于不重写此方法的子类，此方法的默认实现返回与 getMessage()相同的结果。

**语法:**

```
public String getLocalizedMessage()
```

**返回值:**当异常发生时，该方法返回**可投掷对象的特定于地区的描述**。

下面的程序演示了可抛出类的 getLocalizedMessage()方法:

**例 1:**

```
// Java program to demonstrate
// the getLocalizedMessage() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {
            // add the numbers
            addPositiveNumbers(2, -1);
        }
        catch (Exception e) {
            System.out.println("LocalizedMessage = "
                               + e.getLocalizedMessage());
        }
    }

    // method which adds two positive number
    public static void addPositiveNumbers(int a, int b)
        throws Exception
    {

        if (a < 0 || b < 0) {

            throw new Exception("Numbers are not Positive");
        }
        else {

            System.out.println(a + b);
        }
    }
}
```

**Output:**

```
LocalizedMessage = Numbers are not Positive

```

**例 2:**

```
// Java program to demonstrate
// the ensureCapacity() Method.

import java.io.*;

class GFG {

    // Main Method
    public static void main(String[] args)
        throws Exception
    {

        try {
            testException();
        }

        catch (Throwable e) {
            System.out.println("LocalizedMessage of Exception : "
                               + e.getLocalizedMessage());
        }
    }

    // method which throws IndexOutOfBoundsException
    public static void testException()
        throws IndexOutOfBoundsException
    {

        throw new IndexOutOfBoundsException(
            "Forcefully Generated Exception");
    }
}
```

**Output:**

```
LocalizedMessage of Exception : Forcefully Generated Exception

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/throwable . html # getlocalized message()](https://docs.oracle.com/javase/10/docs/api/java/lang/Throwable.html#getLocalizedMessage())