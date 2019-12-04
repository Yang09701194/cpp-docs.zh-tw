---
title: 編譯器錯誤 C2392
ms.date: 11/04/2016
f1_keywords:
- C2392
helpviewer_keywords:
- C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
ms.openlocfilehash: 15fa4a19cdd791ddb3636f30a636cc084bdc4a5f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745001"
---
# <a name="compiler-error-c2392"></a>編譯器錯誤 C2392

' method1 '： managed 或 WinRTtypes 中不支援協變數傳回類型，否則將會覆寫 ' method2 '

當 Windows 執行階段成員函式，或使用[/clr （Common Language Runtime 編譯）](../../build/reference/clr-common-language-runtime-compilation.md)選項進行編譯時，不允許使用協變數傳回類型。

## <a name="example"></a>範例

下列範例會產生 C2392，並示範如何修正此問題。

```cpp
// C2392.cpp
// compile with: /clr
public ref struct B {
public:
   int i;
};

public ref struct D: public B{};

public ref struct B1 {
public:
   virtual B^ mf() {
      B^ pB = gcnew B;
      pB->i = 11;
      return pB;
   }
};

public ref struct D1: public B1 {
public:
   virtual D^ mf() override {  // C2392
   // try the following line instead
   // virtual B^ mf() override {
   // return type D^ is covariant with B^, not allowed with CLR types
      D^ pD = gcnew D;
      pD->i = 12;
      return pD;
   }
};

int main() {
   B1^ pB1 = gcnew D1;
   B^ pB = pB1->mf();
   D^ pD = dynamic_cast<D^>(pB);
}
```
