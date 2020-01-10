---
title: 編譯器錯誤 C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: e46eff4ec2b1afdb309b3c4db89c9283e2fc8971
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757029"
---
# <a name="compiler-error-c2494"></a>編譯器錯誤 C2494

無法從篩選運算式或 __finally/finally 區塊中呼叫 ' 關鍵字 '

您不能在 `__finally` 或 finally 區塊中使用 `keyword`。

下列範例會產生 C2494：

```cpp
// C2494.cpp
#include <malloc.h>

int main() {
   __try {}
   __except ( _alloca(100), 1 ) {}   // C2494
   __try {}
   __finally {
      _alloca(100);   // C2494
   }
}
```

使用 **/clr**時也可能會發生 C2494。

```cpp
// C2494b.cpp
// compile with: /clr
#include <malloc.h>

int main() {
   char * buf;
   try {}
   catch (char * buf2) {}
   finally {
      _alloca(100);   // C2494
   }
}
```
