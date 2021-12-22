# WeakHashMap 包含 Java 中的 Value()方法

> 原文:[https://www . geesforgeks . org/weakashmap-contains value-method-in-Java/](https://www.geeksforgeeks.org/weakhashmap-containsvalue-method-in-java/)

Java . util . WeakHashMap . contains VaLue()方法用于检查 Weakhashmap 中的一个键或多个键是否映射了特定的值。它将值作为参数，如果该值由映射中的任何键映射，则返回真。

**语法:**

```
Weak_Hash_Map.containsValue(*Object Value*)
```

**参数:**该方法只取一个对象类型的参数*值*，并引用其映射应该由映射内任何键检查的值。

**返回值:**如果检测到值的映射，则该方法返回布尔值 true，否则返回 false。

下面的程序说明了 Java . util . Weakhashmap . contains value()方法:

**程序 1:** 将字符串值映射到整数键。

```
// Java code to illustrate the containsValue() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<Integer, String> weak_hash = new WeakHashMap<Integer, String>();

        // Mapping string values to int keys
        weak_hash.put(10, "Geeks");
        weak_hash.put(15, "4");
        weak_hash.put(20, "Geeks");
        weak_hash.put(25, "Welcomes");
        weak_hash.put(30, "You");

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: " + weak_hash);

        // Checking for the Value 'Geeks'
        System.out.println("Is the value 'Geeks' present? " + 
                                     weak_hash.containsValue("Geeks"));

        // Checking for the Value 'World'
        System.out.println("Is the value 'World' present? " + 
                                      weak_hash.containsValue("World"));
    }
}
```

**输出:**

```
Initial Mappings are: {30=You, 15=4, 10=Geeks, 25=Welcomes, 20=Geeks}
Is the value 'Geeks' present? true
Is the value 'World' present? false

```

**程序 2:** 将整数值映射到字符串键。

```
// Java code to illustrate the containsValue() method
import java.util.*;

public class Weak_Hash_Map_Demo {
    public static void main(String[] args)
    {

        // Creating an empty WeakHashMap
        Map<String, Integer> weak_hash = new WeakHashMap<String, Integer>();

        // Mapping int values to string keys
        weak_hash.put("Geeks", 10);
        weak_hash.put("4", 15);
        weak_hash.put("Geeks", 20);
        weak_hash.put("Welcomes", 25);
        weak_hash.put("You", 30);

        // Displaying the WeakHashMap
        System.out.println("Initial Mappings are: " + weak_hash);

        // Checking for the Value '10'
        System.out.println("Is the value '10' present? " +
                                    weak_hash.containsValue(10));

        // Checking for the Value '30'
        System.out.println("Is the value '30' present? " + 
                                    weak_hash.containsValue(30));

        // Checking for the Value '40'
        System.out.println("Is the value '40' present? " +
                                    weak_hash.containsValue(40));
    }
}
```

**输出:**

```
Initial Mappings are: {Welcomes=25, 4=15, You=30, Geeks=20}
Is the value '10' present? false
Is the value '30' present? true
Is the value '40' present? false

```

**注意:**相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。