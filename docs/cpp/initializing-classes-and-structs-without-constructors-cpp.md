---
title: Brace initialization for classes, structs, and unions
description: Use brace initialization with any C++ class, struct or union
ms.date: 11/19/2019
ms.assetid: 3e55c3d6-1c6b-4084-b9e5-221b151402f4
ms.openlocfilehash: 41ff38bc4bcc9ebca913b5e66b5ac2f395044222
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246507"
---
# <a name="brace-initialization"></a>Brace initialization

您不一定需要定義類別的建構函式，尤其是相當簡單的類別。 使用者可以使用統一初始化來初始化類別或結構的物件 (如下列範例所示)：

```cpp
// no_constructor.cpp
// Compile with: cl /EHsc no_constructor.cpp
#include <time.h>

// No constructor
struct TempData
{
    int StationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

// Has a constructor
struct TempData2
{
    TempData2(double minimum, double maximum, double cur, int id, time_t t) :
       stationId{id}, timeSet{t}, current{cur}, maxTemp{maximum}, minTemp{minimum} {}
    int stationId;
    time_t timeSet;
    double current;
    double maxTemp;
    double minTemp;
};

int main()
{
    time_t time_to_set;

    // Member initialization (in order of declaration):
    TempData td{ 45978, time(&time_to_set), 28.9, 37.0, 16.7 };

    // Default initialization = {0,0,0,0,0}
    TempData td_default{};

    // Uninitialized = if used, emits warning C4700 uninitialized local variable
    TempData td_noInit;

    // Member declaration (in order of ctor parameters)
    TempData2 td2{ 16.7, 37.0, 28.9, 45978, time(&time_to_set) };

    return 0;
}
```

Note that when a class or struct has no constructor, you provide the list elements in the order that the members are declared in the class. If the class has a constructor, provide the elements in the order of the parameters. If a type has a default constructor, either implicitly or explicitly declared, you can use default brace initialization (with empty braces). For example, the following class may be initialized by using both default and non-default brace initialization:

```cpp
#include <string>
using namespace std;

class class_a {
public:
    class_a() {}
    class_a(string str) : m_string{ str } {}
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}
double m_double;
string m_string;
};

int main()
{
    class_a c1{};
    class_a c1_1;

    class_a c2{ "ww" };
    class_a c2_1("xx");

    // order of parameters is the same as the constructor
    class_a c3{ "yy", 4.4 };
    class_a c3_1("zz", 5.5);
}
```

If a class has non-default constructors, the order in which class members appear in the brace initializer is the order in which the corresponding parameters appear in the constructor, not the order in which the members are declared (as with `class_a` in the previous example). Otherwise, if the type has no declared constructor, the order in which the members appear in the brace initializer is the same as the order in which they are declared; in this case, you can initialize as many of the public members as you wish, but you cannot skip any member. The following example shows the order that's used in brace initialization when there is no declared constructor:

```cpp
class class_d {
public:
    float m_float;
    string m_string;
    wchar_t m_char;
};

int main()
{
    class_d d1{};
    class_d d1{ 4.5 };
    class_d d2{ 4.5, "string" };
    class_d d3{ 4.5, "string", 'c' };

    class_d d4{ "string", 'c' }; // compiler error
    class_d d5("string", 'c', 2.0 }; // compiler error
}
```

If the default constructor is explicitly declared but marked as deleted, default brace initialization cannot be used:

```cpp
class class_f {
public:
    class_f() = delete;
    class_f(string x): m_string { x } {}
    string m_string;
};
int main()
{
    class_f cf{ "hello" };
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function
}
```

You can use brace initialization anywhere you would typically do initialization—for example, as a function parameter or a return value, or with the **new** keyword:

```cpp
class_d* cf = new class_d{4.5};
kr->add_d({ 4.5 });
return { 4.5 };
```

## <a name="initializer_list-constructors"></a>initializer_list constructors

The [initializer_list Class](../standard-library/initializer-list-class.md) represents a list of objects of a specified type that can be used in a constructor, and in other contexts. You can construct an initializer_list by using brace initialization:

```cpp
initializer_list<int> int_list{5, 6, 7};
```

> [!IMPORTANT]
>  To use this class, you must include the [\<initializer_list>](../standard-library/initializer-list.md) header.

An `initializer_list` can be copied. In this case, the members of the new list are references to the members of the original list:

```cpp
initializer_list<int> ilist1{ 5, 6, 7 };
initializer_list<int> ilist2( ilist1 );
if (ilist1.begin() == ilist2.begin())
    cout << "yes" << endl; // expect "yes"
```

The standard library container classes, and also `string`, `wstring`, and `regex`, have `initializer_list` constructors. The following examples show how to do brace initialization with these constructors:

```cpp
vector<int> v1{ 9, 10, 11 };
map<int, string> m1{ {1, "a"}, {2, "b"} };
string s{ 'a', 'b', 'c' };
regex rgx{'x', 'y', 'z'};
```


## <a name="see-also"></a>請參閱

[類別和結構](../cpp/classes-and-structs-cpp.md)<br/>
[建構函式](../cpp/constructors-cpp.md)
