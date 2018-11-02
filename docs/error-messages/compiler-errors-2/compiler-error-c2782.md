---
title: 編譯器錯誤 C2782
ms.date: 11/04/2016
f1_keywords:
- C2782
helpviewer_keywords:
- C2782
ms.assetid: 8b685422-294d-4f64-9f3d-c14eaf03a93d
ms.openlocfilehash: 58fb298ef188c37ebebea6b5c87fe84daeea8aa6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501383"
---
# <a name="compiler-error-c2782"></a>編譯器錯誤 C2782

'declaration': 樣板參數 'identifier' 是模稜兩可

編譯器無法判斷樣板引數的類型。

下列範例會產生 C2782:

```
// C2782.cpp
template<typename T>
void f(T, T) {}

int main() {
   f(1, 'c');   // C2782
   // try the following line instead
   // f<int>(1, 'c');
}
```

使用泛型時，也會發生 C2782:

```
// C2782b.cpp
// compile with: /clr
generic<typename T> void gf(T, T) { }

int main() {
   gf(1, 'c'); // C2782
   // try the following line instead
   // gf<int>(1, 'c');
}
```