---
title: 編譯器錯誤 C3365
ms.date: 11/04/2016
f1_keywords:
- C3365
helpviewer_keywords:
- C3365
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
ms.openlocfilehash: 355c4530fffa89470ac495aff8bc2822278e2da3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201191"
---
# <a name="compiler-error-c3365"></a>編譯器錯誤 C3365

運算子 'operator' : 類型 'type1' 和 'type2' 的不同運算元

已嘗試撰寫不同類型的委派。  如需委派的詳細資訊，請參閱[如何：定義和使用委派C++（/cli）](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md) 。

## <a name="example"></a>範例

下列範例會產生 C3365：

```cpp
// C3365.cpp
// compile with: /clr
delegate void D1();
delegate void D2(int);

ref class R {
public:
   void f(){}
   void g(int){}
};

int main() {
   D1^ d1 = gcnew D1(gcnew R, &R::f);
   D2^ d2 = gcnew D2(gcnew R, &R::g);
   D1^ d3 = gcnew D1(gcnew R, &R::f);

   d1 += d2;   // C3365
   d1 += d3;   // OK
   d1();
}
```
