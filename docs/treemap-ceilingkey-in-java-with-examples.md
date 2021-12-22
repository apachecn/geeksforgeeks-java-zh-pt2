# Java 中的 TreeMap ceilingKey()带示例

> 原文:[https://www . geesforgeks . org/tree map-ceiling key-in-Java-with-examples/](https://www.geeksforgeeks.org/treemap-ceilingkey-in-java-with-examples/)

**树状图类**的 **ceilingKey()函数**返回大于或等于给定键的**最小键，如果该键不存在，则返回 null。**

**语法:**

```java
public K ceilingKey(K key)
```

**参数:**该方法接受一个强制参数**键**，这是需要搜索的键。

**返回值:**该方法返回大于等于给定键值的**最小键**。
如果没有这样的键，则返回 null。

**异常:**该方法抛出以下异常:

*   **class castexception**–如果指定的键无法与给定的键值进行比较，则抛出。
*   **NullPointRexception**–如果给定键为空，并且映射使用自然排序，或者比较器不允许空值，则抛出。

以下是说明 ceilingKey()方法的示例:

**程序 1:** 演示使用 ceilingKey()方法创建带有比较器的树形图

```java
import java.util.*;

public class Main {
    public static void main(String[] args)
    {

        // creating tree map
        NavigableMap<Integer, String>
            treemap = new TreeMap<Integer,
                                  String>((a, b)
                                              -> ((a > b)
                                                      ? 1
                                                      : ((a == b)
                                                             ? 0
                                                             : -1)));

        // populating tree map
        treemap.put(1, " A ");
        treemap.put(2, " B ");
        treemap.put(3, " C ");
        treemap.put(4, " D ");
        treemap.put(6, " E ");
        try {
            System.out.println("Ceiling key entry for 5: "
                               + treemap.ceilingKey(5));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Ceiling key entry for 5: 6

```

**程序 2:** 演示在没有任何比较器的情况下，对树图使用 ceilingKey()方法

```java
import java.util.*;

public class Main {
    public static void main(String[] args)
    {

        // creating tree map
        NavigableMap<Integer, String>
            treemap = new TreeMap<Integer, String>();

        // populating tree map
        treemap.put(1, " A ");
        treemap.put(2, " B ");
        treemap.put(3, " C ");
        treemap.put(4, " D ");
        treemap.put(6, " E ");
        treemap.put(7, " F ");

        // Since 6 is the least value greater than 5,
        // it is returned as the key.
        System.out.println("Ceiling key entry for 5: "
                           + treemap.ceilingKey(5));
    }
}
```

**Output:**

```java
Ceiling key entry for 5: 6

```

**程序 3:** 演示当 ceilingKey()方法将返回 null 时的用法

```java
import java.util.*;

public class Main {
    public static void main(String[] args)
    {

        // creating tree map
        NavigableMap<Integer, String>
            treemap = new TreeMap<Integer, String>();

        // populating tree map
        treemap.put(1, " A ");
        treemap.put(2, " B ");
        treemap.put(3, " C ");
        treemap.put(4, " E ");
        treemap.put(5, " D ");

        // Since 10 is not present in the Map
        // and neither any Key is present greater than 10
        // Hence this will return null
        System.out.println("Ceiling key entry for 10: "
                           + treemap.ceilingKey(10));
    }
}
```

**Output:**

```java
Ceiling key entry for 10: null

```

**程序 4:** 显示空指针异常

```java
import java.util.*;

public class Main {
    public static void main(String[] args)
    {

        // creating tree map
        TreeMap<Integer, String>
            treemap = new TreeMap<Integer, String>();

        // populating tree map
        treemap.put(2, " two ");
        treemap.put(1, " one ");
        treemap.put(3, " three ");
        treemap.put(6, " six ");
        treemap.put(5, " five ");

        try {
            // returns a NullPointerException
            // as key value can't be null
            // because of natural ordering
            System.out.println("Ceiling key entry for null value : "
                               + treemap.ceilingKey(null));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException

```

**程序 5:** 演示 ClassCastException

```java
import java.util.*;

public class Main {
    public static void main(String[] args)
    {

        // creating tree map
        NavigableMap<Object, String>
            treemap = new TreeMap<Object, String>();

        // populating tree map
        treemap.put(1, " A ");
        treemap.put(2, " B ");
        treemap.put(3, " C ");
        treemap.put(4, " E ");
        treemap.put(5, " D ");

        try {
            // returns ClassCastException
            // as we cannot compare a String object with an Integer object
            System.out.println("Ceiling key entry for \"asd\": "
                               + treemap.ceilingKey(new String("asd")));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.ClassCastException: 
           java.lang.Integer cannot be cast to java.lang.String

```