---
title: 原始指標 (C++)
description: 如何使用原始指標C++
ms.date: 04/21/2020
helpviewer_keywords:
- pointers [C++]
no-loc:
- void
- nullptr
- const
- char
- new
- delete
ms.openlocfilehash: 8ba188154d7395ce7be3878fa9dbee2fde08a130
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032092"
---
# <a name="raw-pointers-c"></a>原始指標 (C++)

*指標*是變數的類型。 它將物件的位址存儲在記憶體中,並用於訪問該物件。 *原始指標*是一個指標,其存留期不受封裝物件(如[智慧指標](smart-pointers-modern-cpp.md))控制的控制。 可以為原始指標分配另一個非指標變數的位址,也可以為其分配值[nullptr](nullptr.md)。 尚未分配值的指標包含隨機數據。

也可以*取消引用*指標以檢索它指向的物件的值。 *成員訪問運算符*提供對物件成員的訪問。

```cpp
    int* p = nullptr; // declare pointer and initialize it
                      // so that it doesn't store a random address
    int i = 5;
    p = &i; // assign pointer to address of object
    int j = *p; // dereference p to retrieve the value at its address
```

指標可以指向型態化物件或**void**。 當程式在記憶體中的[堆](https://wikipedia.org/wiki/Heap)上分配物件時,它將以指標的形式接收該物件的位址。 此類指標稱為*擁有指標*。 必須使用擁有指標(或其副本)在不再需要堆分配的物件時顯式釋放它。 無法釋放記憶體會導致*記憶體洩漏*,並使該記憶體位置對計算機上的任何其他程式不可用。 使用**new** 分配的記憶體必須使用**delete**(或**delete\[]** 釋放)。 有關詳細資訊,請參閱[new與delete運算子](new-and-delete-operators.md)。

```cpp
    MyClass* mc = new MyClass(); // allocate object on the heap
    mc->print(); // access class member
    delete mc; // delete object (please don't forget!)
```

指標(如果未聲明為**const**)可以遞增或遞減以指向記憶體中的另一個位置。 此操作稱為*指標算術*。 它用於 C 樣式編程,用於反覆運算陣列或其他資料結構中的元素。 無法**const** 用指標指向不同的記憶體位置,因此與[參考](references-cpp.md)。 有關詳細資訊,請參閱[const和易失性指標](const-and-volatile-pointers.md)。

```cpp
    // declare a C-style string. Compiler adds terminating '\0'.
    const char* str = "Hello world";

    const int c = 1;
    const int* pconst = &c; // declare a non-const pointer to const int
    const int c2 = 2;
    pconst = &c2;  // OK pconst itself isn't const
    const int* const pconst2 = &c;
    // pconst2 = &c2; // Error! pconst2 is const.
```

在 64 位元作業系統上,指標的大小為 64 位元。 系統的指標大小決定了它可以具有多少可定址記憶體。 指標的所有副本都指向同一記憶體位置。 指標(以及引用)在C++中廣泛使用,以傳遞較大的物件和從函數傳遞。 這是因為複製物件的位址通常比複製整個物件更有效。 定義函數時,將指標參數指定為,**const** 除非您打算修改該函數。 通常,**const** 引用是將物件傳遞給函數的首選方法,除非物件的值**nullptr** 可能是 。

[函數的指標](#pointers_to_functions)允許函數傳遞到其他函數,並用於 C 樣式程式設計中的「回檔」。 現代C++為此使用[lambda 運算式](lambda-expressions-in-cpp.md)。

## <a name="initialization-and-member-access"></a>初始化與成員存取

下面的範例展示如何聲明、初始化和使用原始指標。 它的初始化用於**new** 指向在堆上分配的物件,您必須顯式使用**delete**。 該示例還顯示了與原始指標相關的一些危險。 (請記住,此示例是 C 樣式程式設計,而不是現代C++!

```cpp
#include <iostream>
#include <string>

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

// Accepts a MyClass pointer
void func_A(MyClass* mc)
{
    // Modify the object that mc points to.
    // All copies of the pointer will point to
    // the same modified object.
    mc->num = 3;
}

// Accepts a MyClass object
void func_B(MyClass mc)
{
    // mc here is a regular object, not a pointer.
    // Use the "." operator to access members.
    // This statement modifies only the local copy of mc.
    mc.num = 21;
    std::cout << "Local copy of mc:";
    mc.print(); // "Erika, 21"
}


int main()
{
    // Use the * operator to declare a pointer type
    // Use new to allocate and initialize memory
    MyClass* pmc = new MyClass{ 108, "Nick" };

    // Prints the memory address. Usually not what you want.
    std:: cout << pmc << std::endl;

    // Copy the pointed-to object by dereferencing the pointer
    // to access the contents of the memory location.
    // mc is a separate object, allocated here on the stack
    MyClass mc = *pmc;

    // Declare a pointer that points to mc using the addressof operator
    MyClass* pcopy = &mc;

    // Use the -> operator to access the object's public members
    pmc->print(); // "Nick, 108"

    // Copy the pointer. Now pmc and pmc2 point to same object!
    MyClass* pmc2 = pmc;

    // Use copied pointer to modify the original object
    pmc2->name = "Erika";
    pmc->print(); // "Erika, 108"
    pmc2->print(); // "Erika, 108"

    // Pass the pointer to a function.
    func_A(pmc);
    pmc->print(); // "Erika, 3"
    pmc2->print(); // "Erika, 3"

    // Dereference the pointer and pass a copy
    // of the pointed-to object to a function
    func_B(*pmc);
    pmc->print(); // "Erika, 3" (original not modified by function)

    delete(pmc); // don't forget to give memory back to operating system!
   // delete(pmc2); //crash! memory location was already deleted
}
```

## <a name="pointer-arithmetic-and-arrays"></a>指標算術和陣列

指標和數組密切相關。 當陣列通過值傳遞給函數時,它作為指向第一個元素的指標傳遞。 下面的範例展示式指標與陣列的以下重要屬性:

- 運算元`sizeof`傳回陣列的總大小(以位元組為單位)
- 確定元素數,將總位元組除以一個元素的大小
- 當陣列傳遞給函數時,它將*衰減*為指標類型
- 當`sizeof`應用於指標時,運算符返回指標大小,x86 上為 4 個字節,在 x64 上返回 8 個字節

```cpp
#include <iostream>

void func(int arr[], int length)
{
    // returns pointer size. not useful here.
    size_t test = sizeof(arr);

    for(int i = 0; i < length; ++i)
    {
        std::cout << arr[i] << " ";
    }
}

int main()
{

    int i[5]{ 1,2,3,4,5 };
    // sizeof(i) = total bytes
    int j = sizeof(i) / sizeof(i[0]);
    func(i,j);
}
```

某些算術運算可用於非const指標,使它們指向另一個記憶體位置。 **++** 指標使用**+=**、**-=** 運算碼遞增和**--** 遞減。 此技術可用於陣列,在未鍵入數據的緩衝區中特別有用。 獲取**void****char** 以 (1 位元組) 的大小遞增。 鍵入的指標會按它指向的類型的大小遞增。

下面的範例展示如何使用指標算術存取 Windows 上的點陣圖中的單個圖元。 請注意和**delete****new** 和的引用運算符的使用。

```cpp
#include <Windows.h>
#include <fstream>

using namespace std;

int main()
{

    BITMAPINFOHEADER header;
    header.biHeight = 100; // Multiple of 4 for simplicity.
    header.biWidth = 100;
    header.biBitCount = 24;
    header.biPlanes = 1;
    header.biCompression = BI_RGB;
    header.biSize = sizeof(BITMAPINFOHEADER);

    constexpr int bufferSize = 30000;
    unsigned char* buffer = new unsigned char[bufferSize];

    BITMAPFILEHEADER bf;
    bf.bfType = 0x4D42;
    bf.bfSize = header.biSize + 14 + bufferSize;
    bf.bfReserved1 = 0;
    bf.bfReserved2 = 0;
    bf.bfOffBits = sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); //54

    // Create a gray square with a 2-pixel wide outline.
    unsigned char* begin = &buffer[0];
    unsigned char* end = &buffer[0] + bufferSize;
    unsigned char* p = begin;
    constexpr int pixelWidth = 3;
    constexpr int borderWidth = 2;

    while (p < end)
    {
            // Is top or bottom edge?
        if ((p < begin + header.biWidth * pixelWidth * borderWidth)
            || (p > end - header.biWidth * pixelWidth * borderWidth)
            // Is left or right edge?
            || (p - begin) % (header.biWidth * pixelWidth) < (borderWidth * pixelWidth)
            || (p - begin) % (header.biWidth * pixelWidth) > ((header.biWidth - borderWidth) * pixelWidth))
        {
            *p = 0x0; // Black
        }
        else
        {
            *p = 0xC3; // Gray
        }
        p++; // Increment one byte sizeof(unsigned char).
    }

    ofstream wf(R"(box.bmp)", ios::out | ios::binary);

    wf.write(reinterpret_cast<char*>(&bf), sizeof(bf));
    wf.write(reinterpret_cast<char*>(&header), sizeof(header));
    wf.write(reinterpret_cast<char*>(begin), bufferSize);

    delete[] buffer; // Return memory to the OS.
    wf.close();
}
```

## <a name="opno-locvoid-pointers"></a>void• 指標

指向**void** 原始記憶體位置的指標。 有時有必要使用**void** 指標,例如,在C++代碼和C函數之間傳遞時。

當類型化指標被投射到指標時void,記憶體位置的內容將保持不變。 但是,類型資訊將丟失,因此無法執行增量或遞減操作。 例如,可以將記憶體位置強制轉換為 ,從`MyClass*`到`void*`與傳`MyClass*`回到 。 此類操作本質上是容易出錯的,需要非常小心以避免錯誤。 現代C++阻止在幾乎所有情況下使用void指標。

```cpp

//func.c
void func(void* data, int length)
{
    char* c = (char*)(data);

    // fill in the buffer with data
    for (int i = 0; i < length; ++i)
    {
        *c = 0x41;
        ++c;
    }
}

// main.cpp
#include <iostream>

extern "C"
{
    void func(void* data, int length);
}

class MyClass
{
public:
    int num;
    std::string name;
    void print() { std::cout << name << ":" << num << std::endl; }
};

int main()
{
    MyClass* mc = new MyClass{10, "Marian"};
    void* p = static_cast<void*>(mc);
    MyClass* mc2 = static_cast<MyClass*>(p);
    std::cout << mc2->name << std::endl; // "Marian"

    // use operator new to allocate untyped memory block
    void* pvoid = operator new(1000);
    char* pchar = static_cast<char*>(pvoid);
    for(char* c = pchar; c < pchar + 1000; ++c)
    {
        *c = 0x00;
    }
    func(pvoid, 1000);
    char ch = static_cast<char*>(pvoid)[0];
    std::cout << ch << std::endl; // 'A'
    operator delete(p);
}
```

## <a name="pointers-to-functions"></a><a name="pointers_to_functions"></a>指向函數的指標

在 C 樣式編程中,函數指標主要用於將函數傳遞給其他函數。 此技術允許調用方自定義函數的行為,而無需對其進行修改。 在現代C++中[,lambda 運算式](lambda-expressions-in-cpp.md)提供了相同的功能,具有更大的類型安全性和其他優勢。

函式指標宣告指定指向函數必須有的簽名:

```cpp
// Declare pointer to any function that...

// ...accepts a string and returns a string
string (*g)(string a);

// has no return value and no parameters
void (*x)();

// ...returns an int and takes three parameters
// of the specified types
int (*i)(int i, string s, double d);
```

下面的範例顯示一個函數`combine`,該函數將`std::string`接受 和返回的任何函`std::string`數作為 參數。 根據傳遞給`combine`的函數,它要麼準備或追加字串。

```cpp
#include <iostream>
#include <string>

using namespace std;

string base {"hello world"};

string append(string s)
{
    return base.append(" ").append(s);
}

string prepend(string s)
{
    return s.append(" ").append(base);
}

string combine(string s, string(*g)(string a))
{
    return (*g)(s);
}

int main()
{
    cout << combine("from MSVC", append) << "\n";
    cout << combine("Good morning and", prepend) << "\n";
}
```

## <a name="see-also"></a>另請參閱

[智慧指標](smart-pointers-modern-cpp.md)
[方向運算符: |](indirection-operator-star.md)<br/>
[傳址運算子：&](address-of-operator-amp.md)</br>
[歡迎回到C++](welcome-back-to-cpp-modern-cpp.md)
