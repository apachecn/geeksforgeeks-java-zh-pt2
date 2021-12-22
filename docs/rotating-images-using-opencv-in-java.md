# 在 Java 中使用 OpenCV 旋转图像

> 原文:[https://www . geesforgeks . org/rotating-images-use-opencv-in-Java/](https://www.geeksforgeeks.org/rotating-images-using-opencv-in-java/)

图像旋转是一种常见的图像处理例程，用于以任何所需的角度旋转图像。这有助于图像反转、翻转和获得图像的预期视图。图像旋转在匹配、对齐和其他基于图像的算法中有应用。OpenCV 是一个众所周知的用于图像处理的库。

**进场:**

在切换之前，[为 Java 设置一个 OpenCV 环境](https://docs.opencv.org/2.4/doc/tutorials/introduction/java_eclipse/java_eclipse.html)，以便处理图像，并在之后对图像执行操作。现在，借助 *warpAffine()方法*，在 OpenCV 中执行图像旋转。使用这种技术可以将图像旋转任意角度，为此需要定义围绕哪个点或轴进行旋转。

如前所述，连续执行以下步骤:

1.  确定要旋转的点和旋转角度。
2.  获取源图像的旋转矩阵。
3.  使用获得的旋转矩阵对源图像使用仿射变换。

除了这种方法之外，还有两种以 90 度的倍数(即 90 度、180 度、270 度)旋转图像的方法。仿射变换的计算量要大几十倍。仿射插值并使用大量浮点运算。对于 90 度的倍数角度，以下方法比 *warpAffine()* 更有效。

**可能出现的图像旋转用例**

1.  旋转方法
2.  转置和翻转方法

**所需方法:**

1.  石蜡()
2.  getremotion matrix 2d()
3.  旋转()
4.  翻转()
5.  转置()

方法描述如下:

> 1. **warpAffine()** :对图像应用仿射变换。
> 
> **语法**:
> 
> ```java
> *Imgproc.warpAffine(Mat src, Mat dst, Mat M, Size dsize, int flags)*
> ```
> 
> **参数:**
> 
> *   **src–**输入图像。
> *   **dst**–输出图像的尺寸为 dsize，类型与 src 相同。
> *   **M**–2×3 变换(旋转)矩阵。
> *   **dsize**–输出图像的大小。
> *   **标志**–可选字段。WARP _ INVERSE _ MAP 标志。
>     *   未提供标志时，图像映射为逆时针方向。
>     *   如果设置了 WARP _ INVERSE _ MAP 标志，则图像映射为顺时针方向。

> 2.**getrotationmatrix 2d():**计算 2D 旋转的仿射矩阵。
> 
> **语法:**
> 
> ```java
> *Imgproc.getRotationMatrix2D(Point center, double angle, double scale)*
> ```
> 
> **参数:**
> 
> *   **中心**–源图像中旋转的中心。
> *   **角度**–旋转角度，单位为度。正值表示逆时针旋转
> *   **比例**–各向同性比例因子。

> 3.**旋转():**以 90 度的倍数旋转 2D 阵列。
> 
> **语法:**
> 
> ```java
> *Core.rotate(Mat src, Mat dst, int rotateCode)*
> ```
> 
> **参数:**
> 
> *   **src**–输入阵列。
> *   **dst**–与 src 相同类型的输出阵列。
> *   **旋转代码**–指定如何旋转数组的枚举。
>     *   顺时针旋转 90 度:将图像顺时针旋转 90 度或逆时针旋转 270 度
>     *   逆时针旋转 90 度:将图像逆时针旋转 90 度或顺时针旋转 270 度
>     *   旋转 180 度:旋转 180 度。

> 4.**翻转():** 在垂直、水平或两个轴周围翻转 2D 阵列。
> 
> **语法:**
> 
> ```java
> *Core.flip(Mat src, Mat dst, int flipCode)*
> ```
> 
> **参数:**
> 
> *   **src**–输入阵列。
> *   **dst**–与 src 大小和类型相同的输出阵列。
> *   **翻转代码**–指定如何翻转数组的标志。
>     *   flipCode=0 表示围绕 x 轴翻转。
>     *   动画代码> 0(正值，如，1)表示绕 y 轴翻转。
>     *   翻转代码< 0(负值，如-1)表示绕两个轴翻转。

> 5.**转置():** 转置一个矩阵。
> 
> **语法:**
> 
> ```java
> *Core.transpose(Mat src, Mat dst)*
> ```
> 
> **参数:**
> 
> *   **src**–输入阵列。
> *   **dst**–与 src 相同类型的输出阵列。

插图:

> **输入:**考虑样本输入图像:
> 
> ![](img/7a9901961fee107994ece22058da4a95.png)
> 
> 输入图像
> 
> ```java
> Pseudo Code:
> double angle=45
> Point rotPoint=new Point(src.cols()/2.0, src.rows()/2.0)
> Mat rotMat = Imgproc.getRotationMatrix2D( rotPoint, angle, 1);
> Imgproc.warpAffine(src, dst, rotMat, src.size());
> ```
> 
> 应遵循的步骤-
> 
> *   源图像的中点，
> *   rotPoint，考虑旋转，
> *   旋转角度为 45°。
>     *   旋转矩阵是通过 getRotationMatrix2D()方法得到的。
>     *   仿射变换使用 warpAffine()方法执行。
> *   如下图所示，输入图像将逆时针旋转 45°。
> 
> **输出:**图像如图所示:
> 
> ![](img/f6c9adadd35335eedc1a801e580156ae.png)
> 
> 45 逆时针旋转图像

**样本输入图像:**用于实现目的

![](img/7a9901961fee107994ece22058da4a95.png)

输入图像

**情况 1:旋转方法-** 考虑实现部分的输入图像相同。

使用旋转方法旋转图像需要正确使用 rotatecode。

*   如果角度是 90 度或-270 度
    *   使用旋转代码→顺时针旋转 90 度
*   如果角度是 180°或-180°
    *   使用旋转代码→旋转 _180
*   如果角度是 270°或-90°
    *   使用旋转代码→逆时针旋转 90 度

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// import required packages
import org.opencv.core.Core;
import org.opencv.core.Mat;
import org.opencv.core.Point;
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.imgproc.Imgproc;

// Class to rotate image
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Load library required for OpenCV functions
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);

        // Read an image and store in a Matrix object

        // Local directory from where image is picked
        String file = "C:/opencv/image.jpg";
        Mat src = Imgcodecs.imread(file);

        // Create empty Mat object to store output image
        Mat dst = new Mat();

        // Define Rotation Angle
        double angle = 90;

        // Image rotation according to the angle provided
        if (angle == 90 || angle == -270)

            Core.rotate(src, dst, Core.ROTATE_90_CLOCKWISE);
        else if (angle == 180 || angle == -180)

            Core.rotate(src, dst, Core.ROTATE_180);
        else if (angle == 270 || angle == -90)

            Core.rotate(src, dst,
                        Core.ROTATE_90_COUNTERCLOCKWISE);
        else {

            // Center of the rotation is given by
            // midpoint of source image :
            // (width/2.0,height/2.0)
            Point rotPoint = new Point(src.cols() / 2.0,
                                       src.rows() / 2.0);

            // Create Rotation Matrix
            Mat rotMat = Imgproc.getRotationMatrix2D(
                rotPoint, angle, 1);

            // Apply Affine Transformation
            Imgproc.warpAffine(src, dst, rotMat, src.size(),
                               Imgproc.WARP_INVERSE_MAP);

            // If counterclockwise rotation is required use
            // following: Imgproc.warpAffine(src, dst,
            // rotMat, src.size());
        }

        // Save rotated image

        // Destination where rotated image is saved
        // on local directory
        Imgcodecs.imwrite("C:/opencv/rotated_image.jpg", dst

        // Print message for successful execution of program
        System.out.println("Image Rotated Successfully");
    }
}
```