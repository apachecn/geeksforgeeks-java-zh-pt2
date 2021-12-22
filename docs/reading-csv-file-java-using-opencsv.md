# 使用 OpenCSV 读取 Java 中的 CSV 文件

> 原文:[https://www . geesforgeks . org/reading-CSV-file-Java-using-opencsv/](https://www.geeksforgeeks.org/reading-csv-file-java-using-opencsv/)

逗号分隔值(CSV)文件只是一个普通的纯文本文件，逐列存储数据，并通过分隔符(例如，通常是逗号“，”)将其拆分。

OpenCSV 是一个面向 Java 的 CSV 解析器库。OpenCSV 支持所有你想做的基本 CSV 类型的操作。Java 7 是目前 OpenCSV 支持的最低版本。Java 语言没有为有效处理 CSV 文件提供任何本机支持，所以我们在 Java 中使用 OpenCSV 来处理 CSV 文件。

**如何使用 OpenCSV**

1.对于 maven 项目，您可以在 pom.xml 文件中包含 OpenCSV maven 依赖项。

## 超文本标记语言

```
<dependency>
    <groupId>com.opencsv</groupId>
    <artifactId>opencsv</artifactId>
    <version>4.1</version>
</dependency>
```

2.对于 Gradle 项目，您可以包含 OpenCSV 依赖项。

```
compile group: 'com.opencsv', name: 'opencsv', version: '4.1'
```

3.你可以下载 [OpenCSV Jar](https://sourceforge.net/projects/opencsv/files/opencsv/) 并包含在你的项目类路径中。

**opencsv 的一些有用的类**

1.  **CSVReader–**这个类提供了将 CSV 文件作为字符串数组列表读取的操作。
2.  **CSVWriter–**这个类允许我们将数据写入 CSV 文件。
3.  **CsvToBean–**当您想要从 CSV 文件内容填充 java beans 时，将使用这个类。
4.  **BeanToCsv–**这个类有助于将数据从 java 应用程序导出到 Csv 文件。

**读取 CSV 文件**

要读取 CSV 文件，您需要 CSVReader 类。下面是我们将要阅读的示例 CSV 文件。

```
name, rollno, department, result, cgpa
amar, 42, cse, pass, 8.6
rohini, 21, ece, fail, 3.2
aman, 23, cse, pass, 8.9
rahul, 45, ee, fail, 4.6
pratik, 65, cse, pass, 7.2
raunak, 23, me, pass, 9.1
suvam, 68, me, pass, 8.2
```

**我们可以通过两种方式读取 csv 文件:**

**1。逐行读取数据:**我们来看看如何逐行读取 CSV 文件。为了逐行读取数据，首先我们必须通过传递 CSV 文件的 filereader 对象来构造和初始化 CSVReader 对象。之后我们要调用 CSVReader 对象的 readNext()方法，一行一行的读取数据，如下面的代码所示。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate reading a
// CSV file line by line
public static void readDataLineByLine(String file)
{

    try {

        // Create an object of filereader
        // class with CSV file as a parameter.
        FileReader filereader = new FileReader(file);

        // create csvReader object passing
        // file reader as a parameter
        CSVReader csvReader = new CSVReader(filereader);
        String[] nextRecord;

        // we are going to read data line by line
        while ((nextRecord = csvReader.readNext()) != null) {
            for (String cell : nextRecord) {
                System.out.print(cell + "\t");
            }
            System.out.println();
        }
    }
    catch (Exception e) {
        e.printStackTrace();
    }
}
```

**2。一次读取所有数据:**我们使用 readNext()方法逐个读取 CSV 记录。CSVReader 还提供了一个名为 readAll()的方法，可以一次将所有记录读入一个 List。

```
 List allData = csvReader.readAll(); 
```

当我们默认读取 csv 文件时，头不会被忽略，如上面代码的输出所示。当我们需要跳过列表中的第一个元素时，我们可以在创建 CSVReader 时指定开始行。

```
CSVReader csvReader = 
new CSVReaderBuilder(reader).withSkipLines(1).build();
```

代码:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate reading a
// all data at once
public static void readAllDataAtOnce(String file)
{
    try {
        // Create an object of file reader
        // class with CSV file as a parameter.
        FileReader filereader = new FileReader(file);

        // create csvReader object and skip first Line
        CSVReader csvReader = new CSVReaderBuilder(filereader)
                                  .withSkipLines(1)
                                  .build();
        List<String[]> allData = csvReader.readAll();

        // print Data
        for (String[] row : allData) {
            for (String cell : row) {
                System.out.print(cell + "\t");
            }
            System.out.println();
        }
    }
    catch (Exception e) {
        e.printStackTrace();
    }
}
```

**用不同分隔符读取 CSV 文件**

CSV 文件可以用逗号以外的分隔符分隔，例如分号、管道等。以下示例显示了如何读取由分号分隔的 CSV 文件的数据。

**分号分隔的 CSV 文件示例:**

```
name;rollno;department;result;cgpa
amar;42;cse;pass;8.6
rohini;21;ece;fail;3.2
aman;23;cse;pass;8.9
rahul;45;ee;fail;4.6
pratik;65;cse;pass;7.2
raunak;23;me;pass;9.1
suvam;68;me;pass;8.2
```

对于自定义分隔符，首先创建带有特定解析器字符的 CSVParser。

```
CSVParser parser = new CSVParserBuilder().withSeparator(';').build();
```

然后，我们将使用 withsparser()方法和构造函数创建 CSVReader 对象，并将生成的解析器对象提供给 withsparser 方法的参数。最后调用 build 方法构建对象。

```
CSVReader csvReader = new CSVReaderBuilder(filereader).withCSVParser(parser).build();
```

代码:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// Reading CSV File with different separator
public static void readDataFromCustomSeparator(String file)
{
    try {
        // Create an object of file reader class with CSV file as a parameter.
        FileReader filereader = new FileReader(file);

        // create csvParser object with
        // custom separator semi-colon
        CSVParser parser = new CSVParserBuilder().withSeparator(';').build();

        // create csvReader object with parameter
        // filereader and parser
        CSVReader csvReader = new CSVReaderBuilder(filereader)
                                  .withCSVParser(parser)
                                  .build();

        // Read all data at once
        List<String[]> allData = csvReader.readAll();

        // Print Data.
        for (String[] row : allData) {
            for (String cell : row) {
                System.out.print(cell + "\t");
            }
            System.out.println();
        }
    }
    catch (Exception e) {
        e.printStackTrace();
    }
}
```

**示例–读取两个 csv 文件 result.csv 和 results _ 分号 _Separator.csv**
result . CSV 有默认分隔符'，'但 results _ 分号 _ separator . CSV 有分隔符'；'代替“，”。

代码:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate reading
// two CSV files
// with different separators

import java.io.FileReader;
import java.util.List;
import com.opencsv.*;

public class ReadCSVData {
    private static final String CSV_FILE_PATH
        = "D:\\EclipseWorkSpace\\CSVOperations\\results.csv";
    private static final String CSV_FILE_CUSTOM_SEPARATOR
        = "D:\\EclipseWorkSpace\\CSVOperations\\results_semicolon_Separator.csv";

    public static void main(String[] args)
    {

        System.out.println("Read Data Line by Line With Header \n");
        readDataLineByLine(CSV_FILE_PATH);
        System.out.println("_______________________________________________");

        System.out.println("Read All Data at Once and Hide the Header also \n");
        readAllDataAtOnce(CSV_FILE_PATH);
        System.out.println("_______________________________________________");

        System.out.println("Custom Separator here semi-colon\n");
        readDataFromCustomSeparator(CSV_FILE_CUSTOM_SEPARATOR);
        System.out.println("_______________________________________________");
    }

    public static void readDataLineByLine(String file)
    {

        try {

            // Create an object of filereader class
            // with CSV file as a parameter.
            FileReader filereader = new FileReader(file);

            // create csvReader object passing
            // filereader as parameter
            CSVReader csvReader = new CSVReader(filereader);
            String[] nextRecord;

            // we are going to read data line by line
            while ((nextRecord = csvReader.readNext()) != null) {
                for (String cell : nextRecord) {
                    System.out.print(cell + "\t");
                }
                System.out.println();
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    public static void readAllDataAtOnce(String file)
    {
        try {

            // Create an object of filereader class
            // with CSV file as a parameter.
            FileReader filereader = new FileReader(file);

            // create csvReader object
            // and skip first Line
            CSVReader csvReader = new CSVReaderBuilder(filereader)
                                      .withSkipLines(1)
                                      .build();
            List<String[]> allData = csvReader.readAll();

            // print Data
            for (String[] row : allData) {
                for (String cell : row) {
                    System.out.print(cell + "\t");
                }
                System.out.println();
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    public static void readDataFromCustomSeparator(String file)
    {
        try {
            // Create object of filereader
            // class with csv file as parameter.
            FileReader filereader = new FileReader(file);

            // create csvParser object with
            // custom separator semi-colon
            CSVParser parser = new CSVParserBuilder().withSeparator(';').build();

            // create csvReader object with
            // parameter filereader and parser
            CSVReader csvReader = new CSVReaderBuilder(filereader)
                                      .withCSVParser(parser)
                                      .build();

            // Read all data at once
            List<String[]> allData = csvReader.readAll();

            // print Data
            for (String[] row : allData) {
                for (String cell : row) {
                    System.out.print(cell + "\t");
                }
                System.out.println();
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
_______________________________________________
Read Data Line by Line With Header 

name    rollno    department    result    cgpa    
amar    42    cse    pass    8.6    
rohini    21    ece    fail    3.2    
aman    23    cse    pass    8.9    
rahul    45    ee    fail    4.6    
pratik    65    cse    pass    7.2    
raunak    23    me    pass    9.1    
suvam    68    me    pass    8.2    
_______________________________________________
Read All Data at Once and Hide the Header also 

amar    42    cse    pass    8.6    
rohini    21    ece    fail    3.2    
aman    23    cse    pass    8.9    
rahul    45    ee    fail    4.6    
pratik    65    cse    pass    7.2    
raunak    23    me    pass    9.1    
suvam    68    me    pass    8.2    
_______________________________________________
Custom Separator here semi-colon

name    rollno    department    result    cgpa    
amar    42    cse    pass    8.6    
rohini    21    ece    fail    3.2    
aman    23    cse    pass    8.9    
rahul    45    ee    fail    4.6    
pratik    65    cse    pass    7.2    
raunak    23    me    pass    9.1    
suvam    68    me    pass    8.2    
_______________________________________________
```

在未来的文章中，我们将包括更多使用 OpenCSV 对 CSV 文件的操作。
**参考文献:** [CSVReader 类文档](http://opencsv.sourceforge.net/apidocs/index.html)[OpenCSV 文档](http://opencsv.sourceforge.net/)