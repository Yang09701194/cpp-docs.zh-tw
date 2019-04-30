---
title: 編譯器錯誤 C2876
ms.date: 11/04/2016
f1_keywords:
- C2876
helpviewer_keywords:
- C2876
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
ms.openlocfilehash: e7fcdeaf79728ee99498c69de0205619d16612d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390668"
---
# <a name="compiler-error-c2876"></a>編譯器錯誤 C2876

'class::symbol': 不是所有多載可供存取

所有的多載的形式的基底類別中的函式必須能夠在衍生類別。

下列範例會產生 C2876:

```
// C2876.cpp
// compile with: /c
class A {
public:
   double a(double);
private:
   int a(int);
};

class B : public A {
   using A::a;   // C2876 one overload is private in base class
};
```