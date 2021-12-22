# 使用 OpenCSV

用 Java 编写 CSV 文件

> 原文:[https://www . geesforgeks . org/writing-a-CSV-file-in-Java-using-opencsv/](https://www.geeksforgeeks.org/writing-a-csv-file-in-java-using-opencsv/)

逗号分隔值(CSV)文件只是一个普通的纯文本文件，逐列存储数据，并用分隔符将其拆分(例如，通常是逗号“，”)。

OpenCSV 是一个面向 Java 的 CSV 解析器库。OpenCSV 支持所有你想做的基本 CSV 类型的操作。Java 7 是目前 OpenCSV 支持的最低版本。Java 语言没有为有效处理 CSV 文件提供任何本机支持，所以我们在 Java 中使用 OpenCSV 来处理 CSV 文件。

**如何在项目中添加 OpenCSV？**

*   对于 maven 项目，您可以在 pom.xml 文件中包含 OpenCSV maven 依赖项。

    ```java
    <dependency>
        <groupId>com.opencsv</groupId>
        <artifactId>opencsv</artifactId>
        <version>4.1</version>
    </dependency>
    ```

    *   对于 Gradle 项目，您可以包含 OpenCSV 依赖项。

    ```java
    compile group: 'com.opencsv', name: 'opencsv', version: '4.1'
    ```

    *   You can Download [OpenCSV Jar](https://sourceforge.net/projects/opencsv/files/opencsv/) and include in your project class path.

    <center>**Writing a CSV File**</center>

    *   Write Data Line by line – CSVWriter can write line by line using writeNext() method where a string array is passed with each comma-separated element as a separate entry.
    CODE:

    ```java
    public static void writeDataLineByLine(String filePath)
    {
        // first create file object for file placed at location
        // specified by filepath
        File file = new File(filePath);
        try {
            // create FileWriter object with file as parameter
            FileWriter outputfile = new FileWriter(file);

            // create CSVWriter object filewriter object as parameter
            CSVWriter writer = new CSVWriter(outputfile);

            // adding header to csv
            String[] header = { "Name", "Class", "Marks" };
            writer.writeNext(header);

            // add data to csv
            String[] data1 = { "Aman", "10", "620" };
            writer.writeNext(data1);
            String[] data2 = { "Suraj", "10", "630" };
            writer.writeNext(data2);

            // closing writer connection
            writer.close();
        }
        catch (IOException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
    ```

    **输出:**结果. csv 文件，包含以下数据

    ```java
    "Name", "Class", "Marks"
    "Aman", "10", "620"
    "Suraj", "10", "630"

    ```

    *   Write all Data at once- For witting data at once call writeAll() method of CSVWriter class and pass A List of String[] as the parameter with each String[] representing a line of the file.
    CODE:

    ```java
    public static void writeDataAtOnce(String filePath)
    {

        // first create file object for file placed at location
        // specified by filepath
        File file = new File(filePath);

        try {
            // create FileWriter object with file as parameter
            FileWriter outputfile = new FileWriter(file);

            // create CSVWriter object filewriter object as parameter
            CSVWriter writer = new CSVWriter(outputfile);

            // create a List which contains String array
            List<String[]> data = new ArrayList<String[]>();
            data.add(new String[] { "Name", "Class", "Marks" });
            data.add(new String[] { "Aman", "10", "620" });
            data.add(new String[] { "Suraj", "10", "630" });
            writer.writeAll(data);

            // closing writer connection
            writer.close();
        }
        catch (IOException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
    ```

    **输出:**结果. csv 文件，包含以下数据

    ```java
    "Name", "Class", "Marks"
    "Aman", "10", "620"
    "Suraj", "10", "630"

    ```

    <center>**Writing CSV File with different separator**</center>

    By default, the separator for CSV will be a comma(, ). If you want to make another character as a separator so it can be passed as an argument to CSVWriter class.

    ```java
    Syntax :
    CSVWriter(Writer writer, char separator, char quotechar,
                                  char escapechar, String lineEnd)
    Description : Constructs CSVWriter with supplied separator,
    quote char, escape char and line ending.

    ```

    代码:

    ```java
    public static void writeDataForCustomSeparatorCSV(String filePath)
    {

        // first create file object for file placed at location
        // specified by filepath
        File file = new File(filePath);

        try {
            // create FileWriter object with file as parameter
            FileWriter outputfile = new FileWriter(file);

            // create CSVWriter with '|' as separator
            CSVWriter writer = new CSVWriter(outputfile, '|',
                                             CSVWriter.NO_QUOTE_CHARACTER,
                                             CSVWriter.DEFAULT_ESCAPE_CHARACTER,
                                             CSVWriter.DEFAULT_LINE_END);

            // create a List which contains String array
            List<String[]> data = new ArrayList<String[]>();
            data.add(new String[] { "Name", "Class", "Marks" });
            data.add(new String[] { "Aman", "10", "620" });
            data.add(new String[] { "Suraj", "10", "630" });
            writer.writeAll(data);

            // closing writer connection
            writer.close();
        }
        catch (IOException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
    ```

    **输出:**结果. csv 文件，包含以下数据

    ```java
    Name|Class|Marks
    Aman|10|620
    Suraj|10|630

    ```

    **示例:**
    让我们创建一个 java 程序，它生成一个分号分隔的 csv 文件，并包含作为输入提供的数据。

    ```java
    Input:
    Enter no of rows
    9
    Enter Data
    Name Class Marks
    Aman 10 543
    Amar 10 541
    Sanjeet 10 555
    Luv 10 580
    Ranjeet 10 512
    Rabi 10 540
    Dev 10 333
    Sunny 10 198

    ```

    代码:

    ```java
    // Java program to illustrate
    // for Writing Data in CSV file
    import java.io.*;
    import java.util.*;
    import com.opencsv.CSVWriter;

    public class ResultGenerator {
        private static final String CSV_FILE_PATH
            = "./result.csv";
        public static void main(String[] args)
        {
            addDataToCSV(CSV_FILE_PATH);
        }
        public static void addDataToCSV(String output)
        {
            // first create file object for file placed at location
            // specified by filepath
            File file = new File(output);
            Scanner sc = new Scanner(System.in);
            try {
                // create FileWriter object with file as parameter
                FileWriter outputfile = new FileWriter(file);

                // create CSVWriter with ';' as separator
                CSVWriter writer = new CSVWriter(outputfile, ';',
                                                 CSVWriter.NO_QUOTE_CHARACTER,
                                                 CSVWriter.DEFAULT_ESCAPE_CHARACTER,
                                                 CSVWriter.DEFAULT_LINE_END);

                // create a List which contains Data
                List<String[]> data = new ArrayList<String[]>();

                System.out.println("Enter no of rows");
                int noOfRow = Integer.parseInt(sc.nextLine());
                System.out.println("Enter Data");
                for (int i = 0; i < noOfRow; i++) {
                    String row = sc.nextLine();
                    String[] rowdata = row.split(" ");
                    data.add(rowdata);
                }

                writer.writeAll(data);

                // closing writer connection
                writer.close();
            }
            catch (IOException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }
        }
    }
    ```

    **输出:**结果. csv 文件，包含以下数据

    ```java
    Name;Class;Marks
    Aman;10;543
    Amar;10;541
    Sanjeet;10;555
    Luv;10;580
    Ranjeet;10;512
    Rabi;10;540
    Dev;10;333
    Sunny;10;198

    ```

    在未来的文章中，我们将包括更多使用 OpenCSV 对 CSV 文件的操作。
    **参考:** [OpenCSV 文档](http://opencsv.sourceforge.net/)[CSV writer 类文档](http://opencsv.sourceforge.net/apidocs/com/opencsv/CSVWriter.html#DEFAULT_QUOTE_CHARACTER)