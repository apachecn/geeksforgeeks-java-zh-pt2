# 使用 Java 旋转 PDF 文档中的图像

> 原文:[https://www . geesforgeks . org/rotating-a-image-in-a-pdf-document-use-Java/](https://www.geeksforgeeks.org/rotating-an-image-in-a-pdf-document-using-java/)

在本文中，我们将学习如何使用 Java 旋转 PDF 文档中的图像。对于旋转 PDF 中的图像，我们将使用 iText 库。这些是使用 java 在 PDF 中旋转图像应该遵循的步骤。

**1。创建 PdfWriter 对象**

PdfWriter 类表示 PDF 的文档编写器。这个类的构造函数接受一个字符串，即创建 PDF 的文件的路径。

```
// importing the PdfWriter class. 
import com.itextpdf.kernel.pdf.PdfWriter; 

// path where the pdf is to be created. 
String path = "C:/JavaPdf/rotateImage.pdf"; 
PdfWriter pdfwriter = new PdfWriter(path);
```

2.**创建 PdF 文档对象**

PdfDocument 类是 iText 中表示 PDF Document 的类，要以写模式实例化这个类，需要将类 pdfwriter 的一个对象(即上面代码中的 PdfWriter)传递给它的构造函数。

```
// Creating a PdfDocument object. 
// passing PdfWriter object constructor of pdfDocument. 
PdfDocument pdfdocument = new PdfDocument(pdfwriter); 
```

**3。创建文档对象**

文档类是创建自给自足的 PDF 时的根元素。此类的一个构造函数接受 PdfDocument 类(即 pdfdocument)类型的对象。

```
// Creating a Document and passing pdfDocument object 
Document document = new Document(pdfdocument); 
```

**4。创建图像对象**

我们需要图像对象来管理图像。为了创建一个图像对象，我们需要创建一个图像数据对象。我们可以通过将表示图像路径的字符串参数传递给 ImageDataFactory 类的 create()方法来创建它。现在，我们可以通过将 imageData 对象作为参数传递给 Image 类的构造函数来创建一个 Image 对象。

```
// Create an ImageData object 
String imageFile = "F:/JavaPdf/image.jpg"; 
ImageData data = ImageDataFactory.create(imageFile); 

// Creating an Image object 
Image image = new Image(data);
```

**5。旋转图像**

为了旋转一个图像，我们使用了 setRotationAngle()，我们需要传递一个整数来表示我们想要旋转图像的旋转角度。

```
// Rotating the image 
image.setRotationAngle(90);
```

**6。将图像添加到 PDF 文档**

使用 document 类的 [add()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/list-add-method-in-java-with-examples/&sa=U&ved=2ahUKEwiRhqq3sYbtAhWbzjgGHS9AC7EQFjAAegQIBRAB&usg=AOvVaw1uuVFlV1opg0Yvv-F04TIs) 方法添加图像对象，使用 Document 类的 close()方法关闭文档

```
// Adding image to the document 
document.add(image); 

// Closing the document  
document.close();
```

**示例:**下面是帮助我们理解如何使用 Java 旋转 PDF 文档中的图像的最终代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import com.itextpdf.io.image.ImageData;
import com.itextpdf.io.image.ImageDataFactory;
import com.itextpdf.kernel.pdf.PdfDocument;
import com.itextpdf.kernel.pdf.PdfWriter;
import com.itextpdf.layout.Document;
import com.itextpdf.layout.element.Image;

public class RotateImage {
    public static void main(String args[]) throws Exception
    {

        try {
            // path where the pdf is to be created.
            String path = "F:/JavaPdf/RotateImage.pdf";

            // Creating a PdfWriter
            PdfWriter pdfwriter = new PdfWriter(path);

            // Creating a PdfDocument object.
            // passing PdfWriter object constructor of
            // pdfDocument.
            PdfDocument pdfdocument
                = new PdfDocument(pdfwriter);

            // Creating a Document and passing pdfDocument
            // object
            Document document = new Document(pdfdocument);

            // Create an ImageData object
            String imageFile = "F:/JavaPdf/image.jpg";
            ImageData data
                = ImageDataFactory.create(imageFile);

            // Creating an Image object
            Image image = new Image(data);

            // Creating an Image object
            Image image = new Image(data);

            // Rotating the image
            image.setRotationAngle(90);

            // Adding image to the document
            document.add(image);

            // Closing the document
            document.close();

            System.out.println(
                "Image has been rotated successfully");
        }
        catch (Exception e) {
            System.out.println(
                "failed to rotate the image in the file due to "
                + e);
        }
    }
}
```

**编译并执行**

```
javac RotateImage.java 
java RotateImage
```

**输出**

```
Image has been rotated successfully
```

**PDF**

![Rotate an image](img/1a7ceedfb579178b4611a4afe567d372.png)