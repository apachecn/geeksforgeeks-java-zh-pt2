# 用 Java 打印三角图案

> 原文:[https://www . geesforgeks . org/printing-triangle-pattern-in-Java/](https://www.geeksforgeeks.org/printing-triangle-pattern-in-java/)

给定数字 N，任务是打印以下图案:-

示例:

```
Input : 10
Output :                    
          * 
         * * 
        * * * 
       * * * * 
      * * * * * 
     * * * * * * 
    * * * * * * * 
   * * * * * * * * 
  * * * * * * * * * 
 * * * * * * * * * * 

Input :5
Output :
     * 
    * * 
   * * * 
  * * * * 
 * * * * * 

```

打印上述图案需要嵌套循环。外部循环用于运行作为输入给出的行数。外部循环中的第一个循环用于打印每个星号前的空格。正如你所看到的，当我们向三角形的底部移动时，每行的空格数都在减少，所以这个循环每次迭代少运行一次。外环内的第二个环用于打印星星。正如你所看到的，当我们向三角形的底部移动时，每行的星星数量都在增加，所以这个循环在每次迭代中会多运行一次。如果这个程序是试运行的，就可以达到清晰。

```
// Java Program to print the given pattern
import java.util.*; // package to use Scanner class
class pattern {
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number of rows to be printed");
        int rows = sc.nextInt();

        // loop to iterate for the given number of rows
        for (int i = 1; i <= rows; i++) {

            // loop to print the number of spaces before the star
            for (int j = rows; j >= i; j--) {
                System.out.print(" ");
            }

            // loop to print the number of stars in each row
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }

            // for new line after printing each row
            System.out.println();
        }
    }
}
```