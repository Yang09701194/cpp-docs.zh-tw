---
title: 編譯器錯誤 C2105 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2105
dev_langs:
- C++
helpviewer_keywords:
- C2105
ms.assetid: 19b7f7bc-a9da-4d23-8193-005b6d09274f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b659331779fd6036b9c66ba8b42f3f4c725dc6f6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103765"
---
# <a name="compiler-error-c2105"></a>編譯器錯誤 C2105

'operator' 需要左值

運算子必須是左值做為運算元。

下列範例會產生 C2105:

```
// C2105.cpp
int main() {
   unsigned char * p1 = 0;
   unsigned int * p2 = (unsigned int *)p1;
   p2++;

   unsigned int * p = 0;
   p++;   // ok

   p2 = (unsigned int *)p1;
   ((unsigned int *)p1)++;   // C2105
}
```

下列範例會產生 C2105:

```
// C2105b.cpp
int main() {
   int a[10] = {0};
   int b[10] = {0};
   ++(a , b);   // C2105

   // OK
   ++(a[0] , b[0]);
   ++a[0];
}
```