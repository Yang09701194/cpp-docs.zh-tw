---
title: 編譯器錯誤 C2494 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2494
dev_langs:
- C++
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e651e66ce571ddd084c470b52494235f35f2b008
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066800"
---
# <a name="compiler-error-c2494"></a>編譯器錯誤 C2494

'keyword' 不能從篩選條件運算式內呼叫或 __finally/finally 區塊

您無法使用`keyword`在`__finally`或 finally 區塊。

下列範例會產生 C2494:

```
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

使用時，也可能發生 C2494 **/clr**。

```
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