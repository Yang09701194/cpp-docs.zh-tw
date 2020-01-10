---
title: 編譯器錯誤 C3104
ms.date: 11/04/2016
f1_keywords:
- C3104
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
ms.openlocfilehash: b92a6eade137a1d319ec286afa08f8477ff029d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755852"
---
# <a name="compiler-error-c3104"></a>編譯器錯誤 C3104

不合法的屬性引數

您為屬性指定了不正確引數。

如需詳細資訊，請參閱[屬性參數類型](../../extensions/attribute-parameter-types-cpp-component-extensions.md)。

這項錯誤可能是由於針對 Visual Studio 2005 所做的編譯器一致性工作而產生的結果：將 managed 陣列傳遞至自訂屬性時，陣列的類型已不再從匯總初始化清單推斷。 編譯器現在會要求您指定陣列的類型以及初始化運算式清單。

## <a name="example"></a>範例

下列範例會產生 C3104。

```cpp
// C3104a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104
// try the following line instead
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="example"></a>範例

下列範例會產生 C3104。

```cpp
// C3104b.cpp
// compile with: /clr /c
// C3104 expected
using namespace System;

int func() {
   return 0;
}

[attribute(All)]
ref class A {
public:
   A(int) {}
};

// Delete the following 2 lines to resolve.
[A(func())]
ref class B {};

// OK
[A(0)]
ref class B {};
```
