# Java 中的配对类

> 原文:[https://www.geeksforgeeks.org/pair-class-in-java/](https://www.geeksforgeeks.org/pair-class-in-java/)

在 C++中，我们在实用程序库中有 [std::pair](https://www.geeksforgeeks.org/pair-in-cpp-stl/) ，如果我们想保持一对值在一起，这是非常有用的。我们在 Java 中寻找 pair 的等价类，但是 Pair 类直到 Java 7 才出现。JavaFX 2.2 有 [javafx.util.Pair](http://docs.oracle.com/javafx/2/api/javafx/util/Pair.html) 类，可以用来存储一对。我们需要使用 [javafx.util.Pair](http://docs.oracle.com/javafx/2/api/javafx/util/Pair.html) 类提供的参数化构造函数将这些值存储到 Pair 中。

**注意:**注意 [HashMap/TreeMap](https://www.geeksforgeeks.org/hashmap-treemap-java/) 中使用的<键、值>对。这里，<键，值>简单地指的是存储在一起的一对值。

**JavaFX . util . pair 类提供的方法**

*   **配对(K 键，V 值):**创建新的配对
*   **boolean equals() :** It is used to compare two pair objects. It does a deep comparison, i.e., it compares on the basic of the values (<Key, Value>) which are stored in the pair objects.

    **Example:**

    ```java
    Pair p1 = new Pair(3,4);
    Pair p2 = new Pair(3,4);
    Pair p3 = new Pair(4,4);
    System.out.println(p1.equals(p2) + “ ” + p2.equals(p3));
    ```

    **输出:**
    真假

*   **字符串 toString() :** 此方法将返回该对的字符串表示。
*   **K getKey() :** 它返回该对的密钥。
*   **V getValue() :** 它返回对的值。
*   **int hashCode() :** Generate a hash code for the Pair.

    让我们看看下面的问题。
    **问题陈述:**我们得到了 n 名学生的名字以及他们在测验中获得的相应分数。我们需要找到班上分数最高的学生。

    **注意:你需要在你的机器上安装 Java 8 才能运行下面的程序。**

    ```java
    /* Java program to find a Pair which has maximum score*/
    import javafx.util.Pair;
    import java.util.ArrayList;

    class Test
    {
        /* This method returns a Pair which hasmaximum score*/
        public static Pair <String,Integer>
                  getMaximum(ArrayList < Pair <String,Integer> > l)
        {
            // Assign minimum value initially
            int max = Integer.MIN_VALUE;

            // Pair to store the maximum marks of a 
            // student with its name
            Pair <String, Integer> ans = 
                             new Pair <String, Integer> ("", 0);

            // Using for each loop to iterate array of 
            // Pair Objects
            for (Pair <String,Integer> temp : l)
            {
                // Get the score of Student
                int val = temp.getValue();

                // Check if it is greater than the previous 
                // maximum marks
                if (val > max)
                {
                    max = val;  // update maximum
                    ans = temp; // update the Pair
                }
            }
            return ans;
        }

        // Driver method to test above method
        public static void main (String[] args)
        {
             int n = 5;//Number of Students

            //Create an Array List
            ArrayList <Pair <String,Integer> > l =
                      new ArrayList <Pair <String,Integer> > ();

            /*  Create pair of name of student  with their
                corresponding score and insert into the
                Arraylist */
            l.add(new Pair <String,Integer> ("Student A", 90));
            l.add(new Pair <String,Integer> ("Student B", 54));
            l.add(new Pair <String,Integer> ("Student C", 99));
            l.add(new Pair <String,Integer> ("Student D", 88));
            l.add(new Pair <String,Integer> ("Student E", 89));

            // get the Pair which has maximum value
            Pair <String,Integer> ans = getMaximum(l);

            System.out.println(ans.getKey() + " is top scorer " +
                              "with score of " + ans.getValue());
        }
    }
    ```

    **输出**:

    ```java
    Student C is top scorer with score of 99
    ```

    **注**:上述程序可能无法在在线 IDE 中运行，请使用离线编译器。

    参考文献:[https://docs.oracle.com/javafx/2/api/javafx/util/Pair.html](https://docs.oracle.com/javafx/2/api/javafx/util/Pair.html)T3】

    本文由 **Chirag Agarwal** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论