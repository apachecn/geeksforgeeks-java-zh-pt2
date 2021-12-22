# Java 中的 ResourceBundle 和 ListResourceBundle 类，示例

> 原文:[https://www . geesforgeks . org/resource bundle-and-list resource bundle-Java-class-in-with-examples/](https://www.geeksforgeeks.org/resourcebundle-and-listresourcebundle-class-in-java-with-examples/)

**资源包**和**列表资源包**类是 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)的一部分。这些类旨在帮助程序国际化。

**<u>ResourceBundle</u>** :类 **ResourceBundle** 是一个**抽象**类。它定义了使您能够管理区域设置敏感资源集合的方法。资源包由其家族名称来标识。家族名称中添加了两个字符的小写语言代码，用于指定语言。我们也可以在语言代码后指定国家代码。它是一个两个字符的大写标识符，当链接到资源包名称时，前面有一个下划线。

**等级等级:**

```
java.lang.Object
↳java.util.ResourceBundle
```

**施工人员:**

**1。ResourceBundle()** :默认构造函数，主要设计用于子类和工厂方法。

```
public ResourceBundle()
```

**方法:**

**1。clearCache()** :这个方法从缓存中删除默认类加载器加载的所有资源包。

```
static final void clearCache()
```

**2。containsKey()** :如果传递的字符串参数是调用资源包中的键，则该方法返回 true。

```
boolean containsKey(String k)
```

**3。getBundle()** :这个方法用给定的名称和指定的区域设置加载资源包。

```
static final ResourceBundle getBundle(String familyName)
static final ResourceBundle getBundle(String familyName, Locale loc)
```

**4。setParent()** :此方法将传递的包设置为调用包的父包。在查找的情况下，如果在调用对象中找不到该键，则在父包中查找它。

```
protected void setParent(ResourceBundle parent)
```

**5。getObject()** :此方法从当前资源包或父包中检索并返回与作为参数传递的键相关联的对象。

```
public final Object getObject(String key)
```

**6。getHandleObject()** :这个方法从资源包中返回与给定键关联的对象。如果没有可用的对象，则返回 null。

```
protected abstract Object handleGetObject(String key)
```

**7。getString()** :此方法从当前资源包或父包中检索并返回与作为参数传递的键相关联的字符串。

```
public final String getString(String key)
```

**8。getstringgarray()**:此方法从当前资源包或父包中检索并返回与作为参数传递的键相关联的字符串数组。

```
public final String[] getStringArray(String key)
```

**9。getLocale()** :这个方法返回与当前包关联的 Locale。

```
public Locale getLocale()
```

**10。containsKey()** :这个方法检查一个给定的键是否存在于一个资源包或者它的父包中。

```
public boolean containsKey(String key)
```

**11 时。keySet()** :此方法返回当前束或其父束中所有键的集合。

```
public Set keySet()
```

**<u>listsourcebundle</u>**:是 **ResourceBundle** 的子类。它是一个抽象类，管理键/值对数组中的资源。它只增加了一个新的方法 **getContents()** ，每个子类都必须实现。

**建造商:**

**1。listsourcebundle()**:创建对象的默认构造函数。

```
public ListResourceBundle()
```

**方法:**

**1。getContents()** :这个方法返回一个包含代表资源的键/值对的二维数组。

```
protected abstract Object[][] getContents()
```

**2。handleGetObject()** :这个方法返回与当前包中的键相关联的对象(如果存在的话)。

```
public final Object handleGetObject(String key)
```

**3。getKeys()** :这个方法返回资源包中键的枚举。

```
public Enumeration getKeys()
```

**4。handleKeySet()** :这个方法返回当前资源包中所有键的集合。

```
protected Set handleKeySet()
```

**演示资源束使用的示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Locale;
import java.util.ResourceBundle;
import java.util.ListResourceBundle;

class SampleRB extends ListResourceBundle {
    protected Object[][] getContents()
    {
        Object[][] resources = new Object[3][2];

        resources[0][0] = "title";
        resources[0][1] = "My Program";

        resources[1][0] = "StopText";
        resources[1][1] = "Stop";

        resources[2][0] = "StartText";
        resources[2][1] = "Start";

        return resources;
    }
}
class SampleRB_de extends ListResourceBundle {
    protected Object[][] getContents()
    {
        Object[][] resources = new Object[3][2];

        resources[0][0] = "title";
        resources[0][1] = "Mein Program";

        resources[1][0] = "StopText";
        resources[1][1] = "Anschlag";

        resources[2][0] = "StartText";
        resources[2][1] = "Anfang";

        return resources;
    }
}
public class LRBDemo {
    public static void main(String[] args)
    {
        ResourceBundle rd
            = ResourceBundle
                  .getBundle("SampleRB",
                             Locale.ENGLISH);
        System.out.println("English Version:");
        System.out.println("String for Title key: "
                           + rd.getString("title"));
        System.out.println("String for StopText key: "
                           + rd.getString("StopText"));
        System.out.println("String for StartText key: "
                           + rd.getString("StartText"));

        rd = ResourceBundle
                 .getBundle("SampleRB",
                            Locale.GERMAN);
        System.out.println("\nGerman Version");
        System.out.println("String for Title key: "
                           + rd.getString("title"));
        System.out.println("String for StopText key: "
                           + rd.getString("StopText"));
        System.out.println("String for StartText key: "
                           + rd.getString("StartText"));
    }
}
```

**输出:**

```
English Version:
String for Title key: My Program
String for StopText key: Stop
String for StartText key: Start

German Version
String for Title key: Mein Program
String for StopText key: Anschlag
String for StartText key: Anfang
```

**参考:**T2T4】