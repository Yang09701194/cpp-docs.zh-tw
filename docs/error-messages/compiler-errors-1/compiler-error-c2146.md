---
title: 編譯器錯誤 C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: 8dc7b521243c4eafdc22fab851812b6c12b004cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755911"
---
# <a name="compiler-error-c2146"></a>編譯器錯誤 C2146

語法錯誤：識別碼 ' identifier ' 之前遺漏 ' token '

編譯器必須 `token`，並改為找到 `identifier`。  可能的原因:

1. 拼寫或大小寫錯誤。

1. 識別碼的宣告中遺漏類型規範。

此錯誤可能是因為印刷錯誤所造成。 錯誤[C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md)通常會在此錯誤之前。

## <a name="example"></a>範例

下列範例會產生 C2146。

```cpp
// C2146.cpp
class CDeclaredClass {};

class CMyClass {
   CUndeclared m_myClass;   // C2146
   CDeclaredClass m_myClass2;   // OK
};

int main() {
   int x;
   int t x;   // C2146 : missing semicolon before 'x'
}
```

## <a name="example"></a>範例

針對 Visual Studio .NET 2003 所做的編譯器一致性工作，也會產生此錯誤：遺漏 `typename` 關鍵字。

下列範例會在 Visual Studio .NET 2002 中進行編譯，但在 Visual Studio .NET 2003 中將會失敗：

```cpp
// C2146b.cpp
// compile with: /c
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};

template <typename T>
X<T>::Y func() { }   // C2146

// OK
template <typename T>
typename X<T>::Y func() { }
```

## <a name="example"></a>範例

您也會看到此錯誤的結果，是針對 Visual Studio .NET 2003 進行的編譯器一致性工作：明確特製化不再從主要範本尋找範本參數。

明確特製化中不允許使用來自主要範本的 `T`。 若要讓程式碼在 Visual Studio .NET 2003 和 Visual Studio .NET 中有效，請將特製化中樣板參數的所有實例取代為明確特殊化的類型。

下列範例會在 Visual Studio .NET 中編譯，但在 Visual Studio .NET 2003 中會失敗：

```cpp
// C2146_c.cpp
// compile with: /c
template <class T>
struct S;

template <>
struct S<int> {
   T m_t;   // C2146
   int m_t2;   // OK
};
```
