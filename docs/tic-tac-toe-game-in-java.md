# Java 井字游戏

> 原文:[https://www.geeksforgeeks.org/tic-tac-toe-game-in-java/](https://www.geeksforgeeks.org/tic-tac-toe-game-in-java/)

在井字游戏中，你会看到游戏的方法被实现了。在这个游戏中，将有两个玩家，你在屏幕上有一个印刷板，在那里将显示从 1 到 9 的数字，或者你可以说它是盒子号。现在，您必须为特定的箱号选择 X 或 O。例如，如果你必须选择任何数字，那么 X 或 O 将显示在印刷电路板上，然后转到下一个。任务是创建一个 Java 程序，为两个玩家实现一个 3×3 的井字游戏。

**游戏板:**

```java
      |---|---|---|        
      | 1 | 2 | 3 |
      |-----------|
      | 4 | 5 | 6 |
      |-----------|
      | 7 | 8 | 9 |
      |---|---|---|  

```

**样本输入:**

输入要将 X 放入的插槽号:3

**样本输出:**

```java
      |---|---|---|        
      | 1 | 2 | X |
      |-----------|
      | 4 | 5 | 6 |
      |-----------|
      | 7 | 8 | 9 |
      |---|---|---|  

```

**样本输入:**

现在，轮到 O 了，输入一个槽号将 O 放入:5

**样本输出:**

```java
      |---|---|---|        
      | 1 | 2 | X |
      |-----------|
      | 4 | O | 6 |
      |-----------|
      | 7 | 8 | 9 |
      |---|---|---|  

```

所以，像这样的游戏还会继续下去。

**如何玩游戏:**

*   两位玩家选择 **X** 或 **O** 来标记自己的细胞。
*   将有一个 3×3 的网格，9 个单元中的每个单元都有编号。
*   选择 **X** 的玩家先开始玩。
*   他输入想要放置 **X** 的手机号。
*   现在， **O** 和 **X** 交替进行，直到其中任何一方获胜。
*   **获胜标准:**每当两个玩家中的任何一个用他的符号(X/ O)填满一行/一列/对角线时，他就获胜，游戏结束。
*   如果两个玩家都没有赢，据说比赛以**平局**结束。

**下面是游戏在 Java 中的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A simple program to demonstrate 
// Tic-Tac-Toe Game.
import java.util.*;

public class GFG {

    static String[] board;
    static String turn;

    // CheckWinner method will 
    // decide the combination 
    // of three box given below.
    static String checkWinner()
    {
        for (int a = 0; a < 8; a++) {
            String line = null;

            switch (a) {
            case 0:
                line = board[0] + board[1] + board[2];
                break;
            case 1:
                line = board[3] + board[4] + board[5];
                break;
            case 2:
                line = board[6] + board[7] + board[8];
                break;
            case 3:
                line = board[0] + board[3] + board[6];
                break;
            case 4:
                line = board[1] + board[4] + board[7];
                break;
            case 5:
                line = board[2] + board[5] + board[8];
                break;
            case 6:
                line = board[0] + board[4] + board[8];
                break;
            case 7:
                line = board[2] + board[4] + board[6];
                break;
            }
            //For X winner
            if (line.equals("XXX")) {
                return "X";
            }

            // For O winner
            else if (line.equals("OOO")) {
                return "O";
            }
        }

        for (int a = 0; a < 9; a++) {
            if (Arrays.asList(board).contains(
                    String.valueOf(a + 1))) {
                break;
            }
            else if (a == 8) {
                return "draw";
            }
        }

       // To enter the X Or O at the exact place on board.
        System.out.println(
            turn + "'s turn; enter a slot number to place "
            + turn + " in:");
        return null;
    }

    // To print out the board.
    /* |---|---|---|
       | 1 | 2 | 3 |
       |-----------|
       | 4 | 5 | 6 |
       |-----------|
       | 7 | 8 | 9 |
       |---|---|---|*/

    static void printBoard()
    {
        System.out.println("|---|---|---|");
        System.out.println("| " + board[0] + " | "
                           + board[1] + " | " + board[2]
                           + " |");
        System.out.println("|-----------|");
        System.out.println("| " + board[3] + " | "
                           + board[4] + " | " + board[5]
                           + " |");
        System.out.println("|-----------|");
        System.out.println("| " + board[6] + " | "
                           + board[7] + " | " + board[8]
                           + " |");
        System.out.println("|---|---|---|");
    }

    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);
        board = new String[9];
        turn = "X";
        String winner = null;

        for (int a = 0; a < 9; a++) {
            board[a] = String.valueOf(a + 1);
        }

        System.out.println("Welcome to 3x3 Tic Tac Toe.");
        printBoard();

        System.out.println(
            "X will play first. Enter a slot number to place X in:");

        while (winner == null) {
            int numInput;

           // Exception handling.
           // numInput will take input from user like from 1 to 9.
           // If it is not in range from 1 to 9.
           // then it will show you an error "Invalid input."
            try {
                numInput = in.nextInt();
                if (!(numInput > 0 && numInput <= 9)) {
                    System.out.println(
                        "Invalid input; re-enter slot number:");
                    continue;
                }
            }
            catch (InputMismatchException e) {
                System.out.println(
                    "Invalid input; re-enter slot number:");
                continue;
            }

            // This game has two player x and O.
            // Here is the logic to decide the turn.
            if (board[numInput - 1].equals(
                    String.valueOf(numInput))) {
                board[numInput - 1] = turn;

                if (turn.equals("X")) {
                    turn = "O";
                }
                else {
                    turn = "X";
                }

                printBoard();
                winner = checkWinner();
            }
            else {
                System.out.println(
                    "Slot already taken; re-enter slot number:");
            }
        }

        // If no one win or lose from both player x and O.
        // then here is the logic to print "draw".
        if (winner.equalsIgnoreCase("draw")) {
            System.out.println(
                "It's a draw! Thanks for playing.");
        }

        // For winner -to display Congratulations! message.
        else {
            System.out.println(
                "Congratulations! " + winner
                + "'s have won! Thanks for playing.");
        }
    }
}
```

**输出:**

```java
Below is the output of the above program :
Welcome to 3x3 Tic Tac Toe.
|---|---|---|
| 1 | 2 | 3 |
|-----------|
| 4 | 5 | 6 |
|-----------|
| 7 | 8 | 9 |
|---|---|---|
X will play first. Enter a slot number to place X in:
3
|---|---|---|
| 1 | 2 | X |
|-----------|
| 4 | 5 | 6 |
|-----------|
| 7 | 8 | 9 |
|---|---|---|
O's turn; enter a slot number to place O in:
5
|---|---|---|
| 1 | 2 | X |
|-----------|
| 4 | O | 6 |
|-----------|
| 7 | 8 | 9 |
|---|---|---|
X's turn; enter a slot number to place X in:
6
|---|---|---|
| 1 | 2 | X |
|-----------|
| 4 | O | X |
|-----------|
| 7 | 8 | 9 |
|---|---|---|
O's turn; enter a slot number to place O in:
1
|---|---|---|
| O | 2 | X |
|-----------|
| 4 | O | X |
|-----------|
| 7 | 8 | 9 |
|---|---|---|
X's turn; enter a slot number to place X in:
9
|---|---|---|
| O | 2 | X |
|-----------|
| 4 | O | X |
|-----------|
| 7 | 8 | X |
|---|---|---|
Congratulations! X's have won! Thanks for playing.

```

**运行在 Eclipse IDE 上:**

*   打开 Eclipse IDE。
*   创建一个新的 Java 项目。
*   右键单击 src 文件夹，创建一个新的类，如类名-GFG。
*   现在，编写您的源代码并按 ctrl+s 保存它。
*   现在，要执行该程序，右键单击 src 文件夹，然后单击“作为 Java 应用程序运行”。

你可以查看下面给定的截图，以供参考。

![](img/371614e9034eb4aae78b373c63d0dc22.png)