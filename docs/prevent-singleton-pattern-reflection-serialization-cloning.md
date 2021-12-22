# 如何防止单体模式的反射、序列化和克隆？

> 原文:[https://www . geesforgeks . org/prevent-singleton-pattern-reflection-序列化-克隆/](https://www.geeksforgeeks.org/prevent-singleton-pattern-reflection-serialization-cloning/)

先决条件:[单例模式](https://www.geeksforgeeks.org/singleton-design-pattern-introduction/)

在本文中，我们将看到有哪些概念会破坏类的单例属性，以及如何避免它们。主要有 3 个概念可以打破类的单例属性。我们一个一个来讨论。

1.  **Reflection:** [Reflection](https://www.geeksforgeeks.org/reflection-in-java/) can be caused to destroy singleton property of singleton class, as shown in following example:

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java code to explain effect of Reflection
    // on Singleton property

    import java.lang.reflect.Constructor;

    // Singleton class
    class Singleton 
    {
        // public instance initialized when loading the class
        public static Singleton instance = new Singleton();

        private Singleton() 
        {
            // private constructor
        }
    }

    public class GFG 
    {

        public static void main(String[] args)
        {
            Singleton instance1 = Singleton.instance;
            Singleton instance2 = null;
            try
            {
                Constructor[] constructors = 
                        Singleton.class.getDeclaredConstructors();
                for (Constructor constructor : constructors) 
                {
                    // Below code will destroy the singleton pattern
                    constructor.setAccessible(true);
                    instance2 = (Singleton) constructor.newInstance();
                    break;
                }
            }

            catch (Exception e) 
            {
                e.printStackTrace();
            }

        System.out.println("instance1.hashCode():- " 
                                          + instance1.hashCode());
        System.out.println("instance2.hashCode():- " 
                                          + instance2.hashCode());
        }
    }
    ```

    ```java
    Output:-
    instance1.hashCode():- 366712642
    instance2.hashCode():- 1829164700

    ```

    运行这个类后，您会看到 hashCodes 是不同的，这意味着创建了两个相同类的对象，并且单例模式已经被销毁。

    **克服反射问题:**为了克服反射引起的问题，使用了[枚举](https://www.geeksforgeeks.org/enum-in-java/)，因为 java 在内部确保枚举值只实例化一次。因为 java Enums 是全局可访问的，所以它们可以用于单件。它唯一的缺点是不灵活，即它不允许惰性初始化。

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    //Java program for Enum type singleton
    public enum Singleton 
    {
      INSTANCE;
    }
    ```

    As enums don’t have any constructor so it is not possible for Reflection to utilize it. Enums have their by-default constructor, we can’t invoke them by ourself. **JVM handles the creation and invocation of enum constructors internally.** As enums don’t give their constructor definition to the program, it is not possible for us to access them by Reflection also. Hence, reflection can’t break singleton property in case of enums.
2.  **Serialization:-** [Serialization](https://www.geeksforgeeks.org/serialization-in-java/) can also cause breakage of singleton property of singleton classes. Serialization is used to convert an object of byte stream and save in a file or send over a network. Suppose you serialize an object of a singleton class. Then if you de-serialize that object it will create a new instance and hence break the singleton pattern.

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java code to explain effect of 
    // Serialization on singleton classes
    import java.io.FileInputStream;
    import java.io.FileOutputStream;
    import java.io.ObjectInput;
    import java.io.ObjectInputStream;
    import java.io.ObjectOutput;
    import java.io.ObjectOutputStream;
    import java.io.Serializable;

    class Singleton implements Serializable 
    {
        // public instance initialized when loading the class
        public static Singleton instance = new Singleton();

        private Singleton() 
        {
            // private constructor
        }
    }

    public class GFG 
    {

        public static void main(String[] args) 
        {
            try
            {
                Singleton instance1 = Singleton.instance;
                ObjectOutput out
                    = new ObjectOutputStream(new FileOutputStream("file.text"));
                out.writeObject(instance1);
                out.close();

                // deserialize from file to object
                ObjectInput in 
                    = new ObjectInputStream(new FileInputStream("file.text"));

                Singleton instance2 = (Singleton) in.readObject();
                in.close();

                System.out.println("instance1 hashCode:- "
                                                     + instance1.hashCode());
                System.out.println("instance2 hashCode:- " 
                                                     + instance2.hashCode());
            } 

            catch (Exception e) 
            {
                e.printStackTrace();
            }
        }
    }
    ```

    ```java
    Output:- 
    instance1 hashCode:- 1550089733
    instance2 hashCode:- 865113938

    ```

    如您所见，两个实例的 hashCode 是不同的，因此单例类有两个对象。因此，这个类不再是单一的。

    **克服序列化问题:-** 为了克服这个问题，我们必须实现方法 readResolve()方法。

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java code to remove the effect of 
    // Serialization on singleton classes
    import java.io.FileInputStream;
    import java.io.FileOutputStream;
    import java.io.ObjectInput;
    import java.io.ObjectInputStream;
    import java.io.ObjectOutput;
    import java.io.ObjectOutputStream;
    import java.io.Serializable;

    class Singleton implements Serializable 
    {
        // public instance initialized when loading the class
        public static Singleton instance = new Singleton();

        private Singleton() 
        {
            // private constructor
        }

        // implement readResolve method
        protected Object readResolve()
        {
            return instance;
        }
    }

    public class GFG 
    {

        public static void main(String[] args) 
        {
            try
            {
                Singleton instance1 = Singleton.instance;
                ObjectOutput out 
                    = new ObjectOutputStream(new FileOutputStream("file.text"));
                out.writeObject(instance1);
                out.close();

                // deserialize from file to object
                ObjectInput in 
                    = new ObjectInputStream(new FileInputStream("file.text"));
                Singleton instance2 = (Singleton) in.readObject();
                in.close();

                System.out.println("instance1 hashCode:- "
                                               + instance1.hashCode());
                System.out.println("instance2 hashCode:- "
                                               + instance2.hashCode());
            } 

            catch (Exception e)
            {
                e.printStackTrace();
            }
        }
    }
    ```

    ```java
    Output:- 
    instance1 hashCode:- 1550089733
    instance2 hashCode:- 1550089733

    ```

    上面的两个 hashcodes 是相同的，因此没有创建其他实例。

3.  **Cloning:** [Cloning](https://www.geeksforgeeks.org/clone-method-in-java-2/) is a concept to create duplicate objects. Using clone we can create copy of object. Suppose, we create clone of a singleton object, then it will create a copy that is there are two instances of a singleton class, hence the class is no more singleton.

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java code to explain cloning 
    // issue with singleton
    class SuperClass implements Cloneable
    {
      int i = 10;

      @Override
      protected Object clone() throws CloneNotSupportedException 
      {
        return super.clone();
      }
    }

    // Singleton class
    class Singleton extends SuperClass
    {
      // public instance initialized when loading the class
      public static Singleton instance = new Singleton();

      private Singleton() 
      {
        // private constructor
      }
    }

    public class GFG
    {
      public static void main(String[] args) throws CloneNotSupportedException 
      {
        Singleton instance1 = Singleton.instance;
        Singleton instance2 = (Singleton) instance1.clone();
        System.out.println("instance1 hashCode:- "
                               + instance1.hashCode());
        System.out.println("instance2 hashCode:- " 
                               + instance2.hashCode()); 
      }
    }
    ```

    ```java
    Output :- 
    instance1 hashCode:- 366712642
    instance2 hashCode:- 1829164700

    ```

    两个不同的 hashCode 意味着单例类有两个不同的对象。

    **克服克隆问题:-** 要克服此问题，请重写 clone()方法，并从 CloneNotSupportedException 的克隆方法中抛出一个异常。现在每当用户试图创建单例对象的克隆时，它都会抛出异常，因此我们的类仍然是单例的。

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java code to explain overcome 
    // cloning issue with singleton
    class SuperClass implements Cloneable
    {
      int i = 10;

      @Override
      protected Object clone() throws CloneNotSupportedException 
      {
        return super.clone();
      }
    }

    // Singleton class
    class Singleton extends SuperClass
    {
      // public instance initialized when loading the class
      public static Singleton instance = new Singleton();

      private Singleton() 
      {
        // private constructor
      }

      @Override
      protected Object clone() throws CloneNotSupportedException 
      {
        throw new CloneNotSupportedException();
      }
    }

    public class GFG
    {
      public static void main(String[] args) throws CloneNotSupportedException 
      {
        Singleton instance1 = Singleton.instance;
        Singleton instance2 = (Singleton) instance1.clone();
        System.out.println("instance1 hashCode:- " 
                             + instance1.hashCode());
        System.out.println("instance2 hashCode:- " 
                             + instance2.hashCode()); 
      }
    }
    ```

    ```java
    Output:-
    Exception in thread "main" java.lang.CloneNotSupportedException
        at GFG.Singleton.clone(GFG.java:29)
        at GFG.GFG.main(GFG.java:38)

    ```

    现在我们已经停止用户创建单例类的克隆。如果你没有；如果不想抛出异常，也可以从 clone 方法返回相同的实例。

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```java
    // Java code to explain overcome 
    // cloning issue with singleton
    class SuperClass implements Cloneable
    {
      int i = 10;

      @Override
      protected Object clone() throws CloneNotSupportedException 
      {
        return super.clone();
      }
    }

    // Singleton class
    class Singleton extends SuperClass
    {
      // public instance initialized when loading the class
      public static Singleton instance = new Singleton();

      private Singleton() 
      {
        // private constructor
      }

      @Override
      protected Object clone() throws CloneNotSupportedException 
      {
        return instance;
      }
    }

    public class GFG
    {
      public static void main(String[] args) throws CloneNotSupportedException 
      {
        Singleton instance1 = Singleton.instance;
        Singleton instance2 = (Singleton) instance1.clone();
        System.out.println("instance1 hashCode:- " 
                               + instance1.hashCode());
        System.out.println("instance2 hashCode:- "
                               + instance2.hashCode()); 
      }
    }
    ```

    ```java
    Output:-
    instance1 hashCode:- 366712642
    instance2 hashCode:- 366712642

    ```

    现在，由于两个实例的 hashcode 相同，这意味着它们代表一个实例。

本文由**维沙尔·加尔格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。