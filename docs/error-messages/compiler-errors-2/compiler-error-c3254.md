---
title: 編譯器錯誤 C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 6b9ff41fb4f45d9570869ca90e3c6091cc03a58a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754247"
---
# <a name="compiler-error-c3254"></a>編譯器錯誤 C3254

' explicit override '：類別包含明確覆寫 ' override '，但不是衍生自包含函式宣告的介面

當您[明確覆寫](../../cpp/explicit-overrides-cpp.md)方法時，包含覆寫的類別必須直接或間接衍生自包含要覆寫之函式的類型。

下列範例會產生 C3254：

```cpp
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```
