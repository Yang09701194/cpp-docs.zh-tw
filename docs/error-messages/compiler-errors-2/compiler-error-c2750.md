---
title: 編譯器錯誤 C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 34d19e8e9f51c90c48ec0d429f98bb82e3d829d4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778906"
---
# <a name="compiler-error-c2750"></a>編譯器錯誤 C2750

'type': 無法使用 'new' 的參考類型使用 'gcnew' 代替

若要建立執行個體的 CLR 型別，這會導致要放在記憶體回收堆積上的執行個體，您必須使用[gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md)。

下列範例會產生 C2750:

```
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```