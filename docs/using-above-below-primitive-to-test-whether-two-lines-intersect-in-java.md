# 在 Java 中使用上下图元测试两条线是否相交

> 原文:[https://www . geesforgeks . org/使用-上-下-基元-测试-是否-两条线-在 java 中相交/](https://www.geeksforgeeks.org/using-above-below-primitive-to-test-whether-two-lines-intersect-in-java/)

上下图元是通过比较线的端点来检查线是否相交的方法。这里有一个 JAVA 程序，它使用上面下面的原语来测试两条线是否相交。只有当一条线的一个端点位于另一条线的左端点的左侧，并且其右端点位于另一条线的右端点的右侧时，该方法才返回 true。

**例**T0】

**接近**T0】

下面是上述方法的实现。

## 爪哇

```
// This is a java program to find whether two lines
// intersect or not using above and below primitive
public class Main {
    public static void check(int x1, int x2, int y1, int y2,
                             int p1, int p2, int q1, int q2)
    { // Segment of line 1 is stored as a1

        int a1 = (y2 - y1) * p1 + (x1 - x2) * q1
                 + (x2 * y1 - x1 * y2);

        if (a1 < 0) {
            // Segment of line 2 is stored as a2
            int a2 = (y2 - y1) * p2 + (x1 - x2) * q2
                     + (x2 * y1 - x1 * y2);

            if (a2 >= 0)
                System.out.println("Intersecting");

            else if (a2 < 0)
                System.out.println("Not intersecting");
        }

        else if (a1 > 0) {

            int a2 = (y2 - y1) * p2 + (x1 - x2) * q2
                     + (x2 * y1 - x1 * y2);

            if (a2 <= 0)
                System.out.println("Intersecting");

            else if (a2 > 0)
                System.out.println("Not intersecting");
        }

        // lines are coincinding
        else
            System.out.println(
                "points are lying on the line");
    }
    // Driver Code
    public static void main(String args[])
    {
        // Taking the coordinates of first line as input
        int x1 = 2, y1 = 3;
        int x2 = 6, y2 = 4;

        // Equation of line using slope point form
        System.out.println("Equation 1: (" + (y2 - y1)
                           + ")x+(" + (x1 - x2) + ")y+("
                           + (x2 * y1 - x1 * y2) + ") = 0");

        // Taking the coordinates of second line as input
        int p1 = 3, q1 = 4;
        int p2 = 7, q2 = 1;

        // Equation of line using slope point form
        System.out.println("Equation 2: (" + (q2 - q1)
                           + ")x+(" + (p1 - p2) + ")y+("
                           + (p2 * q1 - p1 * q2) + ") = 0");

        check(x1, x2, y1, y2, p1, p2, q1, q2);
    }
}
```

**输出**

```
Equation 1: (1)x+(-4)y+(10) = 0
Equation 2: (-3)x+(-4)y+(25) = 0
Intersecting
```

**时间复杂度:** O(1)