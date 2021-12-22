# c++中的模板与 Java 中的泛型

> 原文:[https://www . geesforgeks . org/templates-in-c-vs-generics-in-Java/](https://www.geeksforgeeks.org/templates-in-c-vs-generics-in-java/)

在构建大规模项目时，我们需要代码与提供给它的任何类型的数据兼容。那是你写的代码高于其他代码的地方。这里我们的意思是让您编写的代码对于提供给程序的任何类型的数据都是通用的，而不管它的数据类型是什么。这就是 Java 中的泛型和 C++中的类似命名模板派上用场的地方。虽然两者具有相似的功能，但它们在一些地方有所不同。

**[c++中的模板](https://www.geeksforgeeks.org/templates-cpp/)**

用 C++编写泛型程序称为模板。

1.  One of the main features of templates in c++ is the use of metaprogramming. It makes the template signatures of the provided codes different, if C++ provides the ability to implement them.
2.  A template can be either a class or a function.
3.  C++ requires template sources to be added to their titles.
4.  Template specialization can be realized, that is, the specific types and methods of templates can be realized.

```
// CPP program to illustrate Templates
#include <iostream>
#include <string.h>

using namespace std;

template <class T>
class TempClass {

    T value;

public:
    TempClass(T item)
    {
        value = item;
    }

    T getValue()
    {
        return value;
    }
};

int main()
{
    class TempClass<string>* String = 
      new TempClass<string>("Generics vs Templates");

    cout << "Output Values: " << String->getValue() 
         << "\n";

    class TempClass<int>* integer = new TempClass<int>(9);
    cout << "Output Values: " << integer->getValue();
}
```

**输出:**

```
Output Values: Generics vs Templates
Output Values: 9

```